<template>
    <div>
        <h5 class="fw-normal">Fill this form with your credit card details.</h5>
        <b-form>
            <div class="my-5">
                <b-row>
                    <b-col cols="12" md="8" lg="8">
                        <label for="name" class="h3">Card Number</label>
                        <b-form-group>
                            <b-form-input
                            v-model="cardNo"
                            class="input"
                            :state="validateCardNo"
                            type="number"
                            required
                            ></b-form-input>
                            <b-form-invalid-feedback :state="validateCardNo">
                                Please enter a valid 16 digit card number.
                            </b-form-invalid-feedback>
                            <b-form-valid-feedback :state="validateCardNo">
                                Looks Good.
                            </b-form-valid-feedback>
                        </b-form-group>
                    </b-col>
                    <b-col cols="12" md="4" lg="4">
                        <label for="name" class="h3">Expire</label>
                        <b-form-datepicker id="example-datepicker" v-model="expiry" class="mb-2 input" required></b-form-datepicker>
                    </b-col>
                </b-row>
            </div>
            <div class="my-5">
                 <b-row>
                    <b-col cols="12" md="8" lg="8">
                        <label for="name" class="h3">Name</label>
                        <b-form-group id="input-group-2">
                            <b-form-input
                            v-model="name"
                            class="input"
                            :state="validateName"
                            required
                            ></b-form-input>
                            <b-form-invalid-feedback :state="validateName">
                                Please enter a valid name.
                            </b-form-invalid-feedback>
                            <b-form-valid-feedback :state="validateName">
                                Looks Good.
                            </b-form-valid-feedback>
                        </b-form-group>
                    </b-col>
                    <b-col cols="12" md="4" lg="4">
                        <label for="name" class="h3">Code</label>
                        <b-form-group>
                            <b-form-input
                            v-model="code"
                            type="number"
                            class="input"
                            :state="validateCode"
                            required
                            ></b-form-input>
                            <b-form-invalid-feedback :state="validateCode">
                                Please enter valid 3 digit CVV pin.
                            </b-form-invalid-feedback>
                            <b-form-valid-feedback :state="validateCode">
                                Looks Good.
                            </b-form-valid-feedback>
                        </b-form-group>
                    </b-col>
                 </b-row>
                <label for="name" class="h5">The download link will be sent to this mail</label>
            </div>
            <b-button class="w-100 btn-color mb-5" variant="success" @click.prevent="submit"><h3>Pay with Credit Card</h3></b-button>
        </b-form>
    </div>
</template>
<script>
export default {
    data(){
        return {
            cardNo: '',
            expiry: '',
            name: '',
            code: '',
        }
    },
    methods: {
        submit(){
            if(this.validateCardNo && this.validateName && this.validateCode && this.expiry!='')
                this.$emit("moveToNextStep",'s');
        }
    },
    computed: {
        validateCardNo(){
            const re16digit = /^\d{16}$/
            return this.cardNo.match(re16digit)!=null;
        },
        validateName(){
            return this.name.length > 2;
        },
        validateCode(){
            return this.code.length>2 && this.code.length<4;
        }
    }
}
</script>
<style scoped>
.btn-color{
    background: #41e8a8;
    border: #41e8a8;
}
.input{
  background-color: #DCDCDC;
}
</style>
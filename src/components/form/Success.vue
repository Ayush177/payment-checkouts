<template>
    <div class="pb-5">
        <b-form v-if="!success">
            <div class="my-5">
                <label for="amount" class="h2 p-4">Amount</label>
                <b-form-group id="input-group-2">
                    <b-form-input
                    v-model="amount"
                    type="number"
                    class="input"
                    :state="validateAmt"
                    required
                    ></b-form-input>
                    <b-form-invalid-feedback :state="validateAmt">
                        Please enter a valid name.
                    </b-form-invalid-feedback>
                    <b-form-valid-feedback :state="validateAmt">
                        Looks Good.
                    </b-form-valid-feedback>
                </b-form-group>
                <b-button class="w-100 btn-color mt-5" variant="success" @click.prevent="submit"><h3>Pay</h3></b-button>
            </div>
        </b-form>
        <div v-else>
            <img :src="success_logo" class="w-50">
            <h3>Your transaction is successfull</h3>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            success_logo: "https://cdn3.iconfinder.com/data/icons/flat-actions-icons-9/792/Tick_Mark_Dark-512.png",
            amount: '',
            success: false
        }
    },
    methods: {
        submit(){
            if(this.amount>0)
                this.success=true;
        },
    },
    computed: {
        validateAmt(){
            return this.amount>0;
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
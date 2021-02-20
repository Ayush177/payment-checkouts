<template>
    <div>
        <h5 class="fw-normal">Fill this form with your identity.</h5>
        <b-form>
            <div class="my-5">
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
            </div>
            <div class="my-5">
                <label for="name" class="h3">Email</label>
                <b-form-group id="email">
                    <b-form-input
                    id="email"
                    v-model="email"
                    type="email"
                    class="input"
                    :state="validateEmail"
                    required
                    ></b-form-input>
                    <b-form-invalid-feedback :state="validateEmail">
                        Please enter a valid email address.
                    </b-form-invalid-feedback>
                    <b-form-valid-feedback :state="validateEmail">
                        Looks Good.
                    </b-form-valid-feedback>
                </b-form-group>
                <label for="name" class="h5">The download link will be sent to this mail</label>
            </div>
            <b-button class="w-100 btn-color mb-5" variant="success" @click.prevent="submit"><h3>Save</h3></b-button>
        </b-form>
    </div>
</template>
<script>
export default {
    data(){
        return {
            name: '',
            email: '',
        }
    },
    methods: {
        submit(){
            if(this.validateName && this.validateEmail)
                this.$emit("moveToNextStep",'p');
        }
    },
    computed: {
        validateName(){
            return this.name.length > 2;
        },
        validateEmail(){
            var pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
            return this.email.match(pattern)!=null;
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
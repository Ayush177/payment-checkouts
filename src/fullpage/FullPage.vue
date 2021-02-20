<template>
    <div>
        <b-card class="rounded bg-light m-3 align-middle">
            <div>
                <h1 class="fs-1 fw-bolder pt-5 pb-3 px-5">Checkout</h1>
            </div>
            <hr variant="danger"/>
            <tabs :active="active"/>
            <hr />
            <detail-form class="text-secondary px-5 pt-4" @moveToNextStep="moveForward" v-if="active=='d'"/>
            <payment-form class="text-secondary px-5 pt-4" @moveToNextStep="moveForward" v-if="active=='p'"/>
            <success v-if="active=='s'" class="text-center"/>
        </b-card>
    </div>
</template>
<script>
import Tabs from '../components/tabs/Tabs.vue';
import DetailForm from '../components/form/DetailForm.vue';
import PaymentForm from '../components/form/PaymentForm.vue';
import Success from '../components/form/Success.vue';
export default {
    components: {
        Tabs,
        DetailForm,
        PaymentForm,
        Success
    },
    data(){
        return{
            active: 'd'
        }
    },
    methods: {
        moveForward(next){
            this.active=next;
        }
    }
}
</script>
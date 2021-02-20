<template>
    <div>
        <b-row class="text-secondary text-center">
            <b-col cols="12" md="4" lg="4" :class="active=='d' ? 'text-primary' : ''">
                <span class="pr-5 h1 m-auto">
                    <b-icon icon="person" aria-hidden="true"></b-icon>
                </span>
                <h3 class="d-inline">DETAIL</h3>
            </b-col>
            <b-col cols="12" md="4" lg="4" :class="active=='p' ? 'text-primary' : ''">
                <span class="pr-5 h1 m-auto">
                    <b-icon icon="credit-card" aria-hidden="true" class="pr-2 h1 m-auto"></b-icon>
                </span>
                <h3 class="d-inline">PAYMENT</h3>
            </b-col>
            <b-col cols="12" md="4" lg="4" :class="active=='s' ? 'text-primary' : ''">
                <span class="pr-5 h1 m-auto">
                    <b-icon icon="check2" aria-hidden="true" class="pr-2 h1 m-auto"></b-icon>
                </span>
                <h3 class="d-inline">SUCCESS</h3>
            </b-col>
        </b-row>
    </div>
</template>
<script>
export default {
    props: {
        active: {
            required: true
        }
    }
}
</script>
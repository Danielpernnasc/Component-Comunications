<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!service">Please select a Server</p>
        <p v-else>Select #{{ service.id }} selected, Status {{ service.status }}</p>
        <hr>
        <button @click="resetStatus">Change to Normal</button>
    </div>

</template>

<script>
import { serverBus } from '../../main.js';
export default {
    data: function () {
        return{
            service: null
        }
        
    },
    methods: {
        resetStatus() {
        this.service.status = 'Normal';
    }
    },
    created() {
        serverBus.$on('serverSelect', (service) =>{
            this.service = service;
        });
    }
}
</script>

<style>

</style>

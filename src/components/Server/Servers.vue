<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <app-server
            v-for="service in servers"
            :key="service.id"
            :service="service"
            ></app-server>
        </ul>
    </div>
</template>

<script>
import Service from './service.vue';
export default {
    data: function() {
        return {
            servers:[ 
                {id: 1, status: 'Normal'},
                {id: 2, status: 'Critical'},
                {id: 3, status: 'Unknown'},
                {id: 4, status: 'Normal'},
                ]
        };        
    },
    components: {
        appServer: Service
    }
}
</script>

<style>

</style>

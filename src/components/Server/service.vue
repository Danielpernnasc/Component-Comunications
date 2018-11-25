<template>

            <li
                    class="list-group-item"
                    style="cursor: pointer"
                    @click="serverSelect">
                    Server #{{ service.id }}
            </li>
  
</template>

<script>
import { serverBus } from '../../main.js';
export default {
    props: ['service'],
    methods: {
        serverSelect() {
            serverBus.$emit('serverSelect', this.service)

        }
    }

}
</script>

<style>

</style>

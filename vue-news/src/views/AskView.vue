<template>
    <div v-for="(ask, index) in asks" :key="index">{{ ask.title }}</div>
</template>

<script>
import { fetchAskList } from '../api/index'

export default {
    name: 'AskView',
    data() {
        return {
            asks: [],
        }
    },
    created() {
        fetchAskList()
            .then(response => {
                console.log(response);
                this.asks = response.data;
            })
            .catch(error => {
                console.log(error);
            })
    }
}
</script>

<style></style>
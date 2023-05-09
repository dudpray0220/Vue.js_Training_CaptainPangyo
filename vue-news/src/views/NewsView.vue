<template>
    <div v-for="(user, index) in users" :key="index">{{ user.title }}</div>
</template>

<script>
import { fetchNewsList } from '../api/index'

export default {
    name: 'NewsView',
    data() {
        return {
            users: [],
        }
    },
    created() {
        var vm = this;
        fetchNewsList()
            .then(function (response) {
                console.log(response);
                vm.users = response.data;
            })
            .catch(function (error) {
                console.log(error);
            })
    }
}
</script>

<style></style>
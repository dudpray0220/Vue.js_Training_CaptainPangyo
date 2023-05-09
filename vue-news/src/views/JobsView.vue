<template>
    <div v-for="job in jobs" :key="job">{{ job.title }}</div>
</template>

<script>
import { fetchJobsList } from '../api/index'

export default {
    name: 'JobsView',
    data() {
        return {
            jobs: [],
        }
    },
    created() {
        fetchJobsList()
            .then(response => this.jobs = response.data)
            .catch(error => console.log(error))
    }
}
</script>

<style></style>
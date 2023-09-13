<template>
<div>
    <img :src="dataJobs.logo" :alt="dataJobs.company">
    <div>
        <div>
            {{ dataJobs.company }} {{ dataJobs.new }} {{ dataJobs.featured }}
        </div>
        <div>
            {{ dataJobs.position }}
        </div>
        <div>
            {{dataJobs.postedAt }} {{ dataJobs.contract }} {{ dataJobs.location }}
        </div>

    </div>

    <div>
        {{ dataJobs.role }}  {{ dataJobs.level }}
        <div v-for="job in dataJobs.languages" :key="dataJobs.id">
            {{ job }}
        </div>

    </div>
</div>
</template>

<script>
    export default{
        props: ['dataJobs']
    }

</script>

<style>

</style>
<template>
  <header></header>
  <main>
    <jobs v-for="job in data" :key="job.id" :dataJobs="job">
        
    </jobs>
  </main>
</template>

<script>
import jobs from './components/jobs.vue'
import data from './assets/data.json'
export default{
    components:{
        jobs
    },
    data(){
        return{
            data: data
        }
    }
}
</script>

<style>
 *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
 }
 header{
    background-image: url('./assets/images/bg-header-desktop.svg');
    height: 20vh;
    background-color: hsl(180, 29%, 50%);
    
 }
</style>

<template>
  <header></header>
  <main>
    <div class="filter">
      <span v-for="(tag, index) in tags" :key="index">
        <p>{{ tag }}</p> <button class="delete" @click="deleteTag(index)">X</button>
      </span>
      <button class="clear" @click="deleteAllTags">Clear</button>
    </div>
    <jobs v-for="job in data" :key="job.id" :dataJobs="job" @tagsName="tagsToFilter">
        
    </jobs>
  </main>
</template>

<script>
import jobs from './components/jobs.vue'
import data from './static/data.json'
export default{
    components:{
        jobs
    },
    data(){
        return{
            data: data,
            tags: []
        }
    },
    methods:{
      tagsToFilter(value){
        this.tags.push(value)
        console.log(this.tags)
      },
      deleteTag(index){
        this.tags.splice(index, 1)
      },
      deleteAllTags(){
        this.tags.splice(0, this.tags.length)
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
 main{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
 }
 .filter{
  display: flex;
  box-shadow: 2px 10px 20px rgba(0, 0, 0, 0.199);
  height: 60px;
  width: 60vw;
  color: hsl(180, 29%, 50%);
  font-weight: bold;
  font-family: 'League Spartan', sans-serif;
  align-items: center;
  padding: 5px;
  position: relative;
  
  
 }
 .filter span{
  display: flex;
 }
 .filter p{
  background-color:hsla(180, 29%, 50%, 0.199) ;
  padding: 12px;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
  margin-left: 15px;
 }
 .delete{
  background-color: hsl(180, 29%, 50%);
  border: none;
  padding: 8px;
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;
  color: white;
  font-size: large;
  font-weight: bold;
  cursor: pointer;
 }
 .clear{
  color: hsl(180, 29%, 50%);
  font-weight: bold;
  border: none;
  background-color: transparent;
  margin-right: 15px;
  position: absolute;
  right: 0;
 }
 .clear:hover{
  text-decoration: underline hsl(180, 29%, 50%);
  cursor: pointer;
 }
</style>

<template>
<div class="container">
    <img :src="dataJobs.logo" :alt="dataJobs.company">
        <div class="info-job">
        
        <div class="company">
            <p class="company-p">{{ dataJobs.company }}</p>
            <p v-if="dataJobs.new" class="new">New!</p>
            <p v-if="dataJobs.featured " class="feature">Feature</p>
        </div>
        
        <div class="level">
            <p>{{ dataJobs.position }}</p>
        </div>
        <div class="time">
            <p>{{dataJobs.postedAt }}</p>
            <p>{{ dataJobs.contract }}</p>
            <p>{{ dataJobs.location }}</p>
        </div>
        

        </div>

    <div class="tags">
        <div class="area">
            <p @click="tagName(dataJobs.role)">{{ dataJobs.role }}</p>
            <p @click="tagName(dataJobs.level)">{{ dataJobs.level }}</p>
        </div>
        <div class="language" v-for="language in dataJobs.languages" :key="dataJobs.id"> 
            <p @click="tagName(language)">{{ language }}</p>
        </div>

        <div class="tools">
            <p v-for="tool in dataJobs.tools" :key="dataJobs.id" @click="tagName(tool)">
                {{ tool }}
            </p>
        </div>   

    </div>
</div>
</template>

<script>
    export default{
        props: ['dataJobs'],
        methods:{
            tagName(value){
                this.$emit('tagsName', value);
                
            }
        }
    }

</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=League+Spartan&display=swap');

.container{
    display: flex;
    width: 60vw;
    margin-block: 15px;
    justify-content: baseline;
    position: relative;
    border-radius: 5px;
    padding: 20px;
    font-family:'League Spartan', sans-serif;
    box-shadow: 2px 10px 10px rgba(0, 0, 0, 0.199);
    border-left: 4px solid transparent;

}
.container:hover{
    border-left: 4px solid hsl(180, 29%, 50%);
}
.info-job{
    margin-left: 20px;
}

.company{
    display: flex;
    margin-bottom: 10px;
    align-items: center;
}
.company p{
    margin-left: 10px;
    padding: 
}
.company-p{
    font-weight: bold;
    color: hsl(180, 29%, 50%);
}
.new{
    background-color: hsl(180, 29%, 50%);
    color: white;
    padding: 8px 10px;
    border-radius: 30px;
    font-weight: bold;
}
.feature{
    background-color: hsl(180, 14%, 20%);
    color: white;
    padding: 8px 10px;
    border-radius: 30px;
    font-weight: bold;
}
.level{
    margin-bottom: 10px;
}
.level p{
    margin-left: 10px;
    font-weight: bold;
    font-size: large;
}
.level p:hover{
    color: hsl(180, 29%, 50%);
    cursor: pointer;
}
.time{
    display: flex;
}
.time p{
    margin-left: 10px;
    color: hsl(180, 8%, 52%);
    font-size: 15px;
}
.tags{
    display: flex;
    color: hsl(180, 29%, 50%);
    font-weight: bold;
    font-size: large;
    padding: 10px;
    justify-content: space-evenly;
    position: absolute;
    right: 0;
    margin-right: 15px;
    top: 35%;
}
.tags p:hover{
    background-color: hsl(180, 29%, 50%);
    color: white;
    border-radius: 5px;
    cursor: pointer;
}
.area{
    display: flex;
    

}
.area p{
    margin-left: 15px;
    padding: 6px;
}
.language{
    display: flex;
    
}
.language p{
    margin-left: 15px;
    padding: 6px;
}
.tools{
    display: flex;
}
.tools p{
    margin-left: 15px;
    padding: 6px;
}

</style>
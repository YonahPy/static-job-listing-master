<template>
<div class="container">
    <img :src="dataJobs.logo" :alt="dataJobs.company">
        <div class="info-job">
        
        <div class="company">
            <p class="company-p">{{ dataJobs.company }}</p>
            <p>{{ dataJobs.new }}</p>
            <p>{{ dataJobs.featured }}</p>
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
            <p>{{ dataJobs.role }}</p>
            <p>{{ dataJobs.level }}</p>
        </div>
        <div class="tools" v-for="job in dataJobs.languages" :key="dataJobs.id"> 
            <p>{{ job }}</p>
            <p v-for="job in dataJobs.tools" :key="dataJobs.id">{{ job }}</p>   
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
}
.info-job{
    margin-left: 20px;
}

.company{
    display: flex;
    margin-bottom: 10px;
}
.company p{
    margin-left: 10px;
}
.company-p{
    font-weight: bold;
    color: hsl(180, 29%, 50%);
}
.level{
    margin-bottom: 10px;
}
.level p{
    margin-left: 10px;
    font-weight: bold;
    font-size: large;
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
    top: 40%;
}
.area{
    display: flex;
    

}
.area p{
    margin-left: 15px;
}
.tools{
    display: flex;
    
}
.tools p{
    margin-left: 15px;
}

</style>
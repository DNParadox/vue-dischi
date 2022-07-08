<template>
   <main>
        <div class="container">
            <div class="column">
                <DiskMainComponent v-for="(element, index) in discArray" :key="index" :musicObject="element"/>
            </div>
        </div>
   </main>
</template>


<script>
import DiskMainComponent from './DiskMainComponent.vue';
import axios from "axios";

export default {
    name: 'DiskMain',
    components: { 
        DiskMainComponent 
    },
    data() {
        return {
            discArray: []
        }
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
          .then(response => {
            this.discArray = response.data.response
        })
          .catch(error => {
            console.log(error)
        })
    }
}
</script>


<style scoped lang="scss">
main{
    background-color: #1e2d3b;
    height: calc(100vh - 50px)
}
.container {
    width: 60%;
    margin: 0 auto;
    .column {
        color:white;
        padding-block: 2rem;
        display:flex;
        flex-wrap: wrap;
    }
}
</style>
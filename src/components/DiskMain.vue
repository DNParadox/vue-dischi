<template>
    <main>
        <div class="selectcontainer">
            <DiskMainSelect
             @selectGenere="searchGenere"
             @selectCantante="searchAuthor"
              :musicObject="filterSong" />
        </div>
        <div class="container">
            <div class="column">
                <DiskMainComponent v-for="(element, index) in filterSong" :key="index" :musicObject="element" />
            </div>
        </div>
    </main>
</template>


<script>
import DiskMainComponent from './DiskMainComponent.vue';
import DiskMainSelect from './DiskMainSelect.vue'
import axios from "axios";


export default {
    name: 'DiskMain',
    components: {
        DiskMainComponent,
        DiskMainSelect
    },
    data() {
        return {
            discArray: [],
            getApi: 'https://flynn.boolean.careers/exercises/api/array/music',
            valueGenre: '',
            valueAuthor: '',
        }
    },
    mounted() {
        axios.get(this.getApi)
            .then(response => {
                this.discArray = response.data.response
            })
            .catch(error => {
                console.log(error)
            })
    },
    computed: {
        filterSong(){
        if (this.valueGenre === "All" && this.valueAuthor === "All") {
          return this.discArray;
        } else if (this.valueGenre !== "All" && this.valueAuthor === "All"){ 
          return this.discArray.filter(word => {
            return word.genre.includes(this.valueGenre)         
          });
        } else if (this.valueGenre === "All" && this.valueAuthor !== "All"){ 
          return this.discArray.filter(word => {
            return word.author.includes(this.valueAuthor)         
          });
        } else {
          return this.discArray.filter(word => {
            return word.author.includes(this.valueAuthor) && word.genre.includes(this.valueGenre)       
          });
        }      
      },         
      },
      methods: {
        searchGenere(word){
        console.log(word)
        this.valueGenre = word;
      },
      searchAuthor(word){
        this.valueAuthor = word;
      }
      }
    }
</script>


<style scoped lang="scss">
main {
    background-color: #1e2d3b;
    height: calc(100vh - 50px)
}

.container {
    width: 60%;
    margin: 0 auto;

    .column {
        color: white;
        padding-block: 1rem;
        display: flex;
        flex-wrap: wrap;
    }
}

.selectcontainer {
    text-align: center;
    padding-top: 1rem;
}

label {
    color: white;
    padding-right: 10px;
}
</style>
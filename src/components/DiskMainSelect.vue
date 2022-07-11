<template>
<div class="container">
    <label for="genre">Genere:</label>
    <select name="" id="genre">
        <option value="All">All</option>
        <option value="Metal">Metal</option>
        <option value="Rock">Rock</option>
        <option value="Jazz">Jazz</option>
        <option value="Pop">Pop</option>
    </select>


    <!-- Bonus -->

 <select 
      id="stand" 
      @change="switchSelectArt($event)" 
      value="0"
    >
      <option value="All">All</option>
      <option v-for="song,index in musicObject" :key="index" :value="song.author">{{song.author}}</option>
    </select>
</div>

</template>

<script>
export default {
    name: 'DiskMainSelect',
    props: {
        musicObject: Object
    },
    methods: {
      switchSelectGen(select){       
        this.$emit("selectGenere", select.target.value);
      },
      switchSelectArt(select){       
        this.$emit("selectCantante", select.target.value);
      }
    }
}
</script>


<style>
</style>
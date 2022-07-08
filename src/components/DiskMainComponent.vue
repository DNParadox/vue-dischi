<template>
    <div> 
        <figure>
            <img src="" alt="qui immagine alt">
            <figcaption class="title"> {{ musicObject.title }}</figcaption>
            <figcaption class="author">  Bon   Jovi  </figcaption>
            <figcaption class="year">       1983   </figcaption>
        </figure>
    </div>
</template>


<script>
export default {
name: 'DiskMainComponent',
props: {
    musicObject: Object
},
  data () {
    return {
    //   poster: ' ', 
      title: ' ',
      author: ' ',
      genre: ' ',
      year: ' ',
    }
  },
  methods: {
      axiosmethods(e,axios) {
          e.preventDefault();
          axios
          .get('https://flynn.boolean.careers/exercises/api/array/music', {
                poster: this.poster,
                title: this.title,
                author: this.author,
                genre: this.genre,
                year: this.year
          })
          .then(response => (console.log(response.data)))
          .catch(error => console.log(error))
          .finally(() => this.loading = false)
      }
  }
}
</script>

<style>
</style>
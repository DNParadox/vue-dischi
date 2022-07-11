<template>
      <div class="disc"> 
        <figure>
            <img :src="musicObject.poster" :alt="musicObject.title">
            <figcaption class="title">  {{ musicObject.title}}</figcaption>
            <figcaption class="author"> {{ musicObject.author}} </figcaption>
            <figcaption class="year">   {{ musicObject.year}} </figcaption>
        </figure>
    </div>  
</template>


<script>

export default {
name: 'DiskMainComponent',
props: {
    musicObject: Object
},

}
</script>

<style scoped lang="scss">
.disc {
    width: calc(100% / 5);
}
figure { 
    background-color: #2e3a46;
}

figure {
    padding-inline: 0.3rem;
    margin: 0.5rem;
    height: 230px;   
}

img {
    padding-top: 0.9rem;
}
</style>
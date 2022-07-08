<template>
   <main>
        <div class="container">
            <div class="column">
              
                <DiskMainComponent  v-for="element, index in component" :key="index" :musicObject="element"/>
            </div>
        </div>
   </main>
</template>


<script>
import DiskMainComponent from '../components/DiskMainComponent.vue'

export default {
    name: 'DiskMain',
    components: { DiskMainComponent },
    data() {
        return {
            component: DiskMainComponent
        }
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
        padding-block: 3rem;
        display:flex;
        padding-inline: 0.3rem;
    }
}
figure { 
    background-color: #2e3a46;
}

figure {
    padding-inline: 0.3rem;
    margin: 0.5rem;
    
}
</style>
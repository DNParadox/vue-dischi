<template>
    <header>
       <div class="boxlogo">
         <img src="../assets/logo-small.svg" alt="Qui logo">
       </div>
    </header>
</template>


<script>
export default {
name: 'DiskHeader'
}
</script>


<style scoped lang="scss">
header {
    height: 50px;
    background-color: #2e3a46;
    .boxlogo{
        width: 70px;
        padding-left: 1rem;
        display: flex;
        align-items: center;
        height: 100%;
    }
}
</style>
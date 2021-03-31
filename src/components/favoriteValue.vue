<template>
    {{counter}}
    <p>we do more....</p>
</template>


<script>
export default {
    computed:{
        counter(){
            return this.$store.getters['numbers/normalizedCounter']  
        }
    },
}
</script>

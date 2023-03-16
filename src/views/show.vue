<template lang="">
    <div>
        
    </div>
</template>
<script>
// userRoute pour la manupliation
import { useRoute } from 'vue-router'
export default {
    setup(){
        const useRout=useRoute();

        console.log(useRout.params.id)
        return {useRout}
    }
    
}
</script>
<style lang="">
    
</style>
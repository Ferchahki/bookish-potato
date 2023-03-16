<template lang="">
    <div>
        <h1 @click="show = !show">{{ post.title }}</h1>
        <p v-if="show">{{ extract }}</p>
    </div>
</template>
<script>
import { ref,computed,onMounted, onUpdated, onUnmounted} from 'vue'
export default {
    props:['post'],
    setup(props){

        // life cycle hoocks 
        onUnmounted(()=>{
            console.log('One Post onUnmounted')
        })
        onMounted(()=>{
            console.log('One Post onMounted')
        })
        onUpdated(()=>{
            console.log('One Post updated')
        })

        const show =ref(true)

        const extract =computed(()=>props.post.content.substring(0,50)+'....')

        return {extract,show}
    }
}
</script>
<style lang="">
    
</style>
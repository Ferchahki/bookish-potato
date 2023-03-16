<template lang="">

        <h1>list of Posts</h1>
        <div v-for="post in posts" ::key="post.id">
            <OnePost  :post="post" />
        </div>

</template>
<script>
import {ref} from 'vue'
import OnePost from '../components/OnePost'
export default {
    components:{OnePost},
    setup(){
        const posts=ref([
            {
                id:1,
                title:"Learn Angular updated",
                content:"Nowadays, due to the great accessibility to the internet, people seek out and consume news via social media due to its low cost, ease of access, and quick transmission of information"
            },
            {
                id:2,
                title:"Learn Vue js  updated",
                content:"Nowadays, due to the great accessibility to the internet, people seek out and consume news via social media due to its low cost, ease of access, and quick transmission of information"
            },
            {
                id:3,
                title:"Learn React JS  updated",
                content:"Nowadays, due to the great accessibility to the internet, people seek out and consume news via social media due to its low cost, ease of access, and quick transmission of information"
            },
        ])
        
        return {posts}
    

    }
}
</script>
<style lang="">
    
</style>
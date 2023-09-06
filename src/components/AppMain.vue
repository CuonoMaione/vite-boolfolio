<template>
    <div>
    <p v-for="post in posts">
        {{ post.title }}
       
    </p>
    </div>
</template>
<script>
import axios from 'axios';

    export default {
        name:'AppMain',

        data() {
            return {
                posts:[],
                ApiUrl:'http://127.0.0.1:8000/api/posts',
            }
        },

        methods: {
            getPosts(){
                axios.get(this.ApiUrl, {
                    params: {}
                })
                .then((response) => {
                    console.log(response.data.results.data);
                    this.posts = response.data.results.data;
                })
                .catch(function (error) {
                    console.log(error);
                })
                ;  

            }
        },

        created() {
            this.getPosts()
        },
    }
</script>
<style lang="scss">
   div{
    text-align: center;
   }
</style>
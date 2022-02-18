<template>
<div>
    <IndexComponent></IndexComponent>
    <CreateComponent></CreateComponent>
</div>
</template>

<script>
import SinglePostComponent from './SinglePostComponent.vue'
import CreateComponent from './IndexComponent.vue'
import IndexComponent from './CreateComponent.vue'
export default {
    name:'PostComponent',
    components:{
        SinglePostComponent,
        CreateComponent,
        IndexComponent,
    },

    mounted(){
        this.getPosts()
    },

    methods:{
        getPosts(){
            axios.get('/posts')
            .then(function(data){

            })
        }
    },

}
</script>

<style scoped>

</style>

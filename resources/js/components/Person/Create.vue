<template>
  <div class="w-25">
      <div class="mb-3">
          <input type="text" v-model="name" placeholder="name" class="form-control">
      </div>
      <div class="mb-3">
          <input type="number" v-model="age" placeholder="age" class="form-control">
      </div>
      <div class="mb-3">
          <input type="text" v-model="job" placeholder="job" class="form-control">
      </div>
      <div class="mb-3">
          <input :disabled="!isDisabled" @click.prevent="$store.dispatch('store',{ name, age ,job })" type="submit" value="Add" class="btn btn-primary">
      </div>
  </div>
</template>

<script>
import {mapGetters}from 'vuex'
export default {
    name: 'Create',

    data(){
        return {
            name: null,
            job: null,
            age: null,
        }
    },

    mounted(){
        this.$store.commit('setPerson',{name: null, age: null, job: null})
    },
    methods:{
    },
    computed:{
        ...mapGetters({
            isDisabled:'isDisabled',
            person: 'person',
        })
    }
}
</script>

<style>

</style>

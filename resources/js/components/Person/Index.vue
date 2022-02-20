<template>
  <div>
      <table class="table">
          <thead>
              <tr>
                  <th>Name</th>
                  <th>Age</th>
                  <th>Job</th>
                  <th>Edit</th>
                  <th>Delete</th>
              </tr>
          </thead>
          <tbody>
              <tr v-for="person in people">
                  <th>
                      <router-link :to="{name: 'person.show', params:{id: person.id}}">
                        {{ person.name}}
                      </router-link>
                   </th>
                  <th>{{ person.age}}</th>
                  <th>{{ person.job}}</th>
                  <th>
                      <router-link :to="{name: 'person.edit', params:{id: person.id}}">Edit</router-link>
                  </th>
                  <th>
                      <a @click.prevent="$store.dispatch('deletePerson',person.id)" href="" class="btn btn-outline-danger">Delete</a>
                  </th>
              </tr>
          </tbody>
      </table>
  </div>
</template>

<script>
export default {
    name: 'Index',

    mounted(){
        this.$store.dispatch('getPeople')
    },
    methods:{

    },

    computed:{
        people(){
            return this.$store.getters.people
        }
    }
}
</script>

<style>

</style>

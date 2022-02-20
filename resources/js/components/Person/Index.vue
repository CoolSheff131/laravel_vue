<template>
  <div>
      <table class="table">
          <thead>
              <tr>
                  <th>Name</th>
                  <th>Age</th>
                  <th>Job</th>
              </tr>
          </thead>
          <tbody>
              <tr v-for="person in people">
                  <th>{{ person.name}}</th>
                  <th>{{ person.age}}</th>
                  <th>{{ person.job}}</th>
              </tr>
          </tbody>
      </table>
  </div>
</template>

<script>
export default {
name: 'Index',
data(){
    return{
        people: null
    }
},

mounted(){
this.getPeople()
},
methods:{
    getPeople(){
        axios.get('/api/people')
        .then(res=>{
            this.people = res.data
        })
    }
}
}
</script>

<style>

</style>

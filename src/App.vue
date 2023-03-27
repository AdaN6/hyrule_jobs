<template>
<div class="app">
  <!-- Practice A -->
      <!-- <p>
      {{ name }} - {{age}}
      </p>
      <button @click="changeName('Fleur')">Change Name</button>
      <button @click="changeAge(30)">Change Age</button> -->
  <!-- End of Practice A -->
<!-- 
  <p>
    {{ jobs[0].location }}
  </p> -->

  <JobList :jobs="jobs"/>
</div>

</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import JobList from './components/JobList.vue';
import Job from './types/Job';



export default defineComponent({
  name: 'App',
  components: {
    JobList
  },
  setup() {
    // ------------- Practice A -------------
      // ---> reactive
      //   const state = reactive({
        //     name: 'Link',
      //     age: 25 as number | string, 
      //   })

      //   return { ...toRefs(state)}

      // ---> ref

      // const name = ref('Link')
      // // generic argument for two different types of data
      // const age = ref<number | string>(25)

      // return { name,age}
    // -------------End of Practice A -------------
    const jobs = ref<Job[]>([
      {title : 'farm worker', location: 'lon lon rance', salary: 3000, id: '1'},
      { title: 'quarryman', location: 'death mountain', salary: 40000, id: '2' },
      { title: 'flute player', location: 'the lost woods', salary: 35000, id: '3' },
      { title: 'fisherman', location: 'lake hylia', salary: 21000, id: '4' },
      { title: 'prison guard', location: 'gerudo valley', salary: 32000, id: '5' }
    ])

    return { jobs }
  },

    // ------------- Practice A -------------

      // data() {
      //   return {
      //     name: 'Link',
      //     age: 25 as number | string,
      //   }
      // },
    // -------------End of Practice A -------------
  methods: {
    
    // ------------- Practice A -------------
      // ----- for using data &
        // changeName(name: string) {
          //   this.name = name
        //   return name

        // },
        // changeAge(age: number | string) {
          //   this.age = age
        //   return age
        // }
    // -------------End of Practice A -------------

  }
});
</script>

<style>

</style>

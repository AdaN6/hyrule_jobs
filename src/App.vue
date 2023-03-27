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
  <header>
    <div class="title">
      <img src="./assets/heart.svg" alt="side logo">
      <h1>
        Hyrule Jobs
      </h1>
    </div>
    <div class="order">
      <button @click="handleClick('title')">Order by title</button>
      <button @click="handleClick('salary')">Order by salary</button>
      <button @click="handleClick('location')">Order by location</button>
    </div>
  </header>
  <JobList :jobs="jobs" :order="order"/>
</div>

</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import JobList from './components/JobList.vue';
import Job from './types/Job';
import OrderTerm from './types/OrderTerms'



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

    const order = ref<OrderTerm>('title')

    const handleClick = (term: OrderTerm) => {
      order.value = term
    }

    return { jobs, handleClick, order }
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
  header {
    text-align: center;
  }
  header .order {
    margin-top: 20px;
  }
  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }

  header .title{
    display: flex;
    justify-content: center;
  }
  header img {
    width: 60px;
    margin-right: 20px;
  }
  header h1 {
    font-size: 3em;
  }

</style>

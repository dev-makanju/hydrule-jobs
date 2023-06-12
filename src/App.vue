<template>
  <nav>
    <button @click="handleClick('title')">Order By Title</button>
    <button @click="handleClick('salary')">Order By Salary</button>
    <button @click="handleClick('location')">Order By Location</button>
    <JobList :jobs="jobs" :order="order"/>
  </nav>
  <router-view/>
</template>

<script lang="ts">
  import { defineComponent , ref } from 'vue';
  import Jobs from "@/types/jobs"
  import JobList from "@/components/JobList.vue";
  import OrderType from "@/types/OrderType";

  export default defineComponent({
    name: "App",
    components:{JobList},
    setup() {
      const jobs = ref<Jobs[]>([
        {
          title:'Food Vendor',
          location: 'lagos',
          salary: 50000
        },
        {
          title:'Content writer',
          location: 'lagos',
          salary: 50000
        },
        {
          title:'Backend Developer',
          location: 'lagos',
          salary: 50000
        },
        {
          title:'Frontend Developer',
          location: 'lagos',
          salary: 50000
        },
      ]);

      const order = ref<OrderType>('title') 
      
      const handleClick = ( term: OrderType) => {
        order.value = term
      }

      return {
        jobs,
        order,
        handleClick
      }
    }
  })

</script>


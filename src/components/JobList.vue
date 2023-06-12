<template>
  <div class="job-list">
     <p>Ordered by {{ order }}</p>
     <ul>
       <li v-for="(job , index) in orderedData" :key="index">
         {{ job.title }}
         {{ job.salary }}
         {{ job.location }}
       </li>
     </ul>
  </div>  
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue';
import Job from "@/types/jobs";
import OrderType from "@/types/OrderType"

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    },
    order: {
      required: true,
      type: String as PropType<OrderType>
    }
  },
  setup(props){
    const orderedData = computed( () => {
      return [...props.jobs].sort((a: Job,b: Job) => {
         return a[props.order] > b[props.order] ? 1 : -1; 
      })
    })

    return { orderedData }
  }
})
</script>

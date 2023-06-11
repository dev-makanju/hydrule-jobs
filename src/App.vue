<template>
  <nav>
    <JobList :jobs="jobs"/>
  </nav>
  <router-view/>
</template>

<script lang="ts">
  import { defineComponent , ref } from 'vue';
  import Jobs from "@/types/jobs"
  import JobList from "@/components/JobList.vue";

  export default defineComponent({
    name: "App",
    components:{JobList},
    setup() {
      const jobs = ref<Jobs[]>([
        {
          name:'Oluwafemi',
          age: 42,
        },
        {
          name:'Oluwakemi',
          age: 42,
        },
        {
          name:'Olamide',
          age: 42,
        },
        {
          name:'Ayomitide',
          age: 42,
        },
      ]);

      return {
        jobs
      }
    }
  })

</script>


<template>
    <div class="job-list">
        <ul>
            <li v-for="job in jobs" :key="job.id">
                <h2> {{job.title}} in {{job.location}} </h2>
                <div class="salary">
                    <p>
                        {{job.salary}} pounds
                    </p>
                </div>
                <div class="description">
                    <p>this is just a mockup description. Please kindly take it as a template to see how it should be previewed. Thank you!</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Job from '@/types/Job'

export default defineComponent({
   props: {
    jobs: {
        required: true,
        type: Array as PropType<Job[]>,
    }
   }
})
</script>

<style>

</style>
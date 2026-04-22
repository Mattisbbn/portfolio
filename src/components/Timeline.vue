<script setup>
import TimelineElement from './TimelineElement.vue';

defineProps({
    timelineId: {
        type: String,
        default: 'school-timeline',
    },
    entries: {
        type: Array,
        default: () => [],
    },
});
</script>


<template>
    <div :id="timelineId" class="ms-auto me-auto timeline grid-white-trigger">
        <TimelineElement v-for="entry in entries" :key="`${timelineId}-${entry.title}`" :title="entry.title"
            :degree="entry.degree" :location="entry.location" :period="entry.period" :degreeIcon="entry.degreeIcon"
            :locationIcon="entry.locationIcon" :periodIcon="entry.periodIcon" />
    </div>

</template>
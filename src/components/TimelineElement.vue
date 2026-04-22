<script setup>
import { Icon } from '@iconify/vue';

defineProps({
    title: {
        type: String,
        required: true,
    },
    degree: {
        type: String,
        required: true,
    },
    location: {
        type: String,
        required: true,
    },
    period: {
        type: String,
        required: true,
    },
    degreeIcon: {
        type: String,
        default: 'fa:graduation-cap',
    },
    locationIcon: {
        type: String,
        default: 'fa:map-marker',
    },
    periodIcon: {
        type: String,
        default: 'fa:calendar',
    },
});
</script>

<template>
    <div class="border-l-6 border-primary relative">
        <span class="rounded-full h-6.25 w-[25px] top-[0px] left-[-16px] bg-primary absolute"></span>
        <div class="ms-4 pb-2">
            <h3 class="font-bold text-xl mb-3 ">{{ title }}</h3>
            <p class="text-gray-500 mb-1.5 text-lg flex items-center gap-2 ">
                <Icon :icon="degreeIcon" class="text-xl w-8" />{{ degree }}
            </p>
            <p class="text-gray-500 mb-1.5 text-lg flex items-center gap-2 ">
                <Icon :icon="locationIcon" class="text-xl w-8" />{{ location }}
            </p>
            <p class="text-gray-500 mb-1.5 text-lg flex items-center gap-2 ">
                <Icon :icon="periodIcon" class="text-xl w-8" />{{ period }}
            </p>
        </div>
    </div>
</template>
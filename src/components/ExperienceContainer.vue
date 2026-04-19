<script setup>
import { ref } from 'vue';
import { Icon } from '@iconify/vue';
import ExperienceButton from './ExperienceButton.vue';

const activeTab = ref('scolaire');


</script>

<template>
    <div>
        <div class="flex mt-8 gap-4 justify-center">
            <ExperienceButton name="Scolaire" @click="activeTab = 'scolaire'">
                <template #icon>
                    <Icon icon="fa:graduation-cap" class="text-2xl text-bright-gray-900" />
                </template>
            </ExperienceButton>

            <ExperienceButton name="Professionnel" @click="activeTab = 'professionnel'">
                <template #icon>
                    <Icon icon="fa:briefcase" class="text-2xl text-bright-gray-900" />
                </template>
            </ExperienceButton>
        </div>

    </div>
</template>
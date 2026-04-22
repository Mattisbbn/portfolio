<script setup>
import { computed, ref } from 'vue';
import { Icon } from '@iconify/vue';

import ExperienceButton from './ExperienceButton.vue';
import Timeline from './Timeline.vue';

const activeTab = ref('scolaire');

const timelines = {
    scolaire: {
        id: 'school-timeline',
        entries: [
            {
                title: 'MyDigitalSchool',
                degree: 'Bachelor CDA',
                location: 'Belle-Beille',
                period: 'Septembre 2025 - Actuellement',
                degreeIcon: 'fa:graduation-cap',
                locationIcon: 'fa:map-marker',
                periodIcon: 'fa:calendar',
            },
            {
                title: 'École Supérieure des Pays de Loire',
                degree: 'BTS SIO SLAM',
                location: 'Belle-Beille',
                period: '2023-2025',
                degreeIcon: 'fa:graduation-cap',
                locationIcon: 'fa:map-marker',
                periodIcon: 'fa:calendar',
            },
            {
                title: 'Saint Aubin La Salle',
                degree: 'BAC PRO systemes Numériques',
                location: 'Verrieres-sur-Anjou',
                period: '2020-2023',
                degreeIcon: 'fa:graduation-cap',
                locationIcon: 'fa:map-marker',
                periodIcon: 'fa:calendar',
            },
        ],
    },
    professionnel: {
        id: 'professional-timeline',
        entries: [
            {
                title: "CAF d'Ille-et-Vilaine",
                degree: "Alternance - Concepteur Développeur",
                location: 'Rennes',
                period: 'Novembre 2025 - Actuellement',
                degreeIcon: 'fa:briefcase',
                locationIcon: 'fa:map-marker',
                periodIcon: 'fa:calendar',
            },
            {
                title: 'Akoufen',
                degree: 'Alternance - Développeur web',
                location: 'Brissac-Quincé',
                period: 'Septembre 2024 - Aout 2025',
                degreeIcon: 'fa:briefcase',
                locationIcon: 'fa:map-marker',
                periodIcon: 'fa:calendar',
            },
            {
                title: 'Leclerc Drive',
                degree: 'Job étudiant - Employé drive',
                location: 'Pont-de-Cé',
                period: 'Mai 2024 - juillet 2024',
                degreeIcon: 'fa:briefcase',
                locationIcon: 'fa:map-marker',
                periodIcon: 'fa:calendar',
            },
            {
                title: 'Electroniques Services',
                degree: 'Stage - Électronicien',
                location: 'Saint-Melaine-sur-Aubance',
                period: 'Novembre 2022 - Janvier 2023 | Mai 2022',
                degreeIcon: 'fa:briefcase',
                locationIcon: 'fa:map-marker',
                periodIcon: 'fa:calendar',
            },
        ],
    },
};

const activeTimeline = computed(() => timelines[activeTab.value] ?? timelines.scolaire);
</script>

<template>
    <div class="w-full">
        <div class="mt-8 flex flex-wrap justify-center gap-4">
            <ExperienceButton name="Scolaire" @click="activeTab = 'scolaire'" :active="activeTab === 'scolaire'">
                <template #icon>
                    <Icon icon="fa:graduation-cap" class="text-xl text-bright-gray-900" />
                </template>
            </ExperienceButton>

            <ExperienceButton name="Professionnel" @click="activeTab = 'professionnel'"
                :active="activeTab === 'professionnel'">
                <template #icon>
                    <Icon icon="fa:briefcase" class="text-xl text-bright-gray-900" />
                </template>
            </ExperienceButton>
        </div>

        <div class="my-auto flex mt-12 ">
            <Timeline :timeline-id="activeTimeline.id" :entries="activeTimeline.entries" />
        </div>
    </div>
</template>

<template>
  <div class="flex flex-auto mx-auto justify-center items-center bg-gray-100">
    <div class="overflow-y-auto w-full" style="max-height: 600px;">
      <table class="table-auto border-collapse border text-white w-96">
        <thead class="bg-gray-800 z-10 border-t">
          <tr>
            <th class="sticky top-0 px-4 py-2 border-b border-gray-900 bg-red-600 font-title">Skill Area</th>
            <th v-for="(skills, country) in countrySkills" :key="country" class="sticky top-0 px-4 py-2 border-b border-gray-900 bg-red-600 font-title">{{ country }}</th>
            <th class="sticky top-0 px-4 py-2 border-b border-gray-900 bg-red-600 font-title">Total of Participating Countries</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="skill in skillAreas" :key="skill">
            <td class="px-4 py-6 border-b border-gray-300 text-gray-950 font-title">{{ mapSkillName(skill) }}</td>
            <td v-for="(skills, country) in countrySkills" :key="country + skill" class="px-4 py-2 text-center border-b border-gray-300">
              <span v-if="skills[skill] === 1">✅</span>
            </td>
            <td class="px-4 py-2 text-center border-b border-gray-300 text-gray-950">{{ totalParticipants(skill) }}</td>
          </tr>
        </tbody>
        <tfoot class="sticky bottom-0 bg-yellow-500 z-10">
          <tr>
            <td class="px-4 py-2 text-center border-t border-b border-gray-300 font-bold">Total Participation</td>
            <td v-for="(skills, country) in countrySkills" :key="'total-' + country" class="px-4 py-2 text-center border-t border-b border-gray-300 font-bold">{{ totalCountryParticipation(country) }}</td>
            <td class="px-4 py-2 text-center border-t border-b border-gray-300 font-bold"></td>
            <!-- {{ overallParticipation }} -->
          </tr>
        </tfoot>
      </table>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import { countrySkills, skillAreas } from '/data/skills.js';

const skillMappings = {
  DDDigitalGameArt: '3D Digital Game Art',
  Industrial40SkillsDemo: 'Industrial 4.0 '
};

const mapSkillName = (skill) => {
  return skillMappings[skill] || skill.replace(/([a-z0-9])([A-Z])/g, '$1 $2').replace(/([A-Z])([A-Z][a-z])/g, '$1 $2');
};

const overallParticipation = computed(() => Object.values(countrySkills).reduce((acc, skills) => acc + Object.values(skills).reduce((sum, skill) => sum + skill, 0), 0));

const totalParticipants = (skill) => {
  return Object.values(countrySkills).reduce((acc, skills) => acc + (skills[skill] || 0), 0);
};

const totalCountryParticipation = (country) => {
  return Object.values(countrySkills[country]).reduce((acc, skill) => acc + skill, 0);
};
</script>

<style scoped>
.table-auto {
  margin: 0 auto;
}
</style>

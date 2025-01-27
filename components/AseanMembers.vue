<template>
<div class="relative bg-blue-950 py-30 flex flex-row flex-wrap items-center justify-center" style="background: url('/box1.png') right center no-repeat; background-size: cover;">
    <div class="flex flex-row space-x-4 pt-10">
        <img src="/bpoutline.png" alt="World Skills Logo" class="w-20">
        <img src="/tesdaoutline.png" alt="World Skills Logo" class="w-20">
    </div>
    <h1 class="text-center text-5xl font-bold text-gray-100 mt-4 pb-14 w-full">PHILIPPINES AS THE 14th <br>WORLD SKILLS ASEAN HOST IN 2025</h1>
</div>
<section class="body-font bg-gray-100 text-gray-400 pb-36">
    
  <div class="container mx-auto px-5 pb-24 pt-10" style="background-image: url('/aseanflagsbg.png'); background-repeat: no-repeat; background-size: cover; background-attachment: fixed;">
        <div class="mb-20 flex w-full flex-row items-center justify-center text-left pb-4" data-aos="fade-down">
            <img src="/aseaniconhd.png" alt="Logo" class="w-20 pt-10">
            <div class="flex flex-col ml-4">
                <h1 class="title-font font-light text-xl text-gray-800">1st Organizing Committee Meeting:</h1>
                <h1 class="title-font font-strong text-4xl text-gray-800">Introduction of Members of the ASEAN</h1>
                <p class="text-base leading-relaxed lg:w-2/3 text-gray-800">Heads of Delegations / Official Delegates</p>
            </div>
        </div>

    <div class="-m-4 flex flex-wrap" data-aos="fade-up">
      <!-- Loop through ASEAN members -->
      <div
        v-for="member in members"
        :key="member.id"
        class="p-4 md:w-1/2 lg:w-1/5"
        @click="openModal(member.id)"
      >
        <div class="flex h-full flex-col items-center text-center">
          <img
            alt="team"
            class="mb-4 h-36 w-full flex-shrink-0 rounded-lg object-cover object-center transition duration-700 ease-in-out hover:scale-105 border-2 border-gray-950 hover:border-indigo-500"
            :src="member.flag"
          />
          <div class="w-full">
            <h2 class="title-font text-sm font-medium text-gray-800">{{ member.name }}</h2>
            <h3 class="-mt-1 text-gray-700">{{ member.position }}</h3>
            <h2 class="-mt-1 text-gray-700">{{ member.country }}</h2>
          </div>
        </div>
      </div>
  
      <!-- Modal Components -->
      <Modal
        v-for="member in members"
        :key="'modal-' + member.id"
        :id="'modal-' + member.id"
        :image="member.image"
        :name="member.name"
        :position="member.position"
        :description="member.description"
        :backgroundImage="'/asean/place/pl' + member.country.toLowerCase() + '.png'"
        ref="modals"
      />
      </div>
    </div>
  </section>
</template>
  
  <script setup>
  import { ref } from 'vue';
  import Modal from '~/components/Modal.vue';
  
  // Define members data
  const members = [
    {
      id: 'brunei',
      name: 'Dr. Hj Mohd Zamri HJ Sabli',
      position: 'Head of Delegations',
      country: 'Brunei',
      flag: '/asean/flag/brunei.webp',
      image: '/asean/focals/sabli.png',
      description: `The Head of Delegation of Brunei Darussalam expressed gratitude to the Philippines for
                            hosting the inaugural organizing committee meeting for WorldSkills ASEAN 2025 and
                            acknowledged the significance of the competition since its inception in 1995. The
                            speaker highlighted the vital role of Technical and Vocational Education and Training
                            (TVET) in enhancing productivity, reducing poverty, and preparing individuals for the
                            workforce. Brunei's participation underscores its commitment to developing a skilled
                            workforce and promoting economic and social progress. The delegation will compete in
                            three skill areas: ICT, Construction and Building Technology, and Social and Personal
                            Services.`,
    },
    {
    id: 'cambodia',
    name: 'Mr. Chan Vichet',
    position: 'Head of Delegations',
    country: 'Cambodia',
    flag: '/asean/flag/cambodia.png',
    image: '/asean/focals/vichet.png',
    backgroundImage: '/asean/place/plcambodia.png',
    description: `The speaker, on behalf of the Cambodian Delegation, extends greetings and gratitude to all present and the Philippine government for hosting the 1st Organizing Committee Meeting for the 14th ASEAN Skills Competition 2025. They highlight the growth of the competition since its inception in 1995, noting its expansion in terms of skills areas, competitors, TVET institutions, and international participation. The ASEAN Skills Competition is recognized for promoting the development of quality vocational skills, work values, and fostering cooperation between various sectors. The speaker looks forward to exchanging knowledge during the meeting to ensure the success of the upcoming competition. Finally, they express thanks again to the Philippine government and wish the participants success in the meeting.`,
  },
  {
    id: 'indonesia',
    name: 'Mr. Mohammad Amir Syarifuddin',
    position: 'Head of Delegation / Official Delegate',
    country: 'Indonesia',
    flag: '/asean/flag/indonesia.webp',
    image: '/asean/focals/amir.png',
    backgroundImage: '/asean/place/plindonesia.png',
    description: `Representing the Indonesian delegation, begins by thanking the Philippine government for their warm hospitality and expressing their pleasure in attending the 1st Organizing Committee Meeting (OCM) for the 14th WorldSkills ASEAN Competition in 2025. They emphasize the importance of skills and knowledge in shaping the future, particularly for the youth who are seen as future leaders and innovators. The speaker highlights the significance of the WorldSkills ASEAN Competition in promoting vocational skills, youth competitiveness, and regional collaboration. They express confidence in the success of the event under the leadership of the Philippines and look forward to productive discussions during the meeting. The remarks conclude with a final expression of gratitude and well wishes.`,
  },
  {
    id: 'lao',
    name: 'Mr. Khornsy Mahavong',
    position: 'Head of Delegation',
    country: 'Lao PDR',
    flag: '/asean/flag/lao.jpg',
    image: '/asean/focals/mahavong.png',
    backgroundImage: '/asean/place/laoplace.png',
    description: `Representing the Lao PDR delegation, expresses gratitude for the opportunity to attend the 1st Organizing Committee Meeting for the 14th ASEAN Skills Competition in the Philippines. They extend warm greetings to all present. The speaker emphasizes the importance of regional cooperation in upgrading vocational skills across ASEAN member states, highlighting the role of skill competitions in strengthening TVET and national competitiveness, as well as promoting global competitiveness. The Lao PDR delegation is eager to participate in the ASEAN Skills Competition to empower youth, enhance their skills, and provide opportunities for future growth at both regional and international levels. The speaker concludes by expressing confidence in the success of the meeting and appreciation for the warm hospitality from the Philippines.`,
  },
  {
    id: 'malaysia',
    name: 'Mrs. Faizah binti Harun',
    position: 'Head of Delegation',
    country: 'Malaysia',
    flag: '/asean/flag/malaysia.png',
    image: '/asean/focals/faizah.png',
    backgroundImage: '/asean/place/plmalaysia.png',
    description: `Representing the Malaysian delegation, expresses pride and gratitude for the opportunity to address the 1st Organizing Committee Meeting of the 14th WorldSkills ASEAN Competition. They acknowledge the efforts of the organizers and reflect on Malaysia’s history with the competition, highlighting the country's role in hosting the event in 1995, 2008, and 2016. Malaysia’s strong participation in the competition is noted, with impressive achievements such as 60 gold, 30 silver, and 50 bronze medals from 1993 to 2023, underscoring the country's commitment to vocational education and skills development.
    The speaker emphasizes the importance of uniting under the WorldSkills and ASEAN platforms to promote skills mastery and technical training, inspiring future generations of professionals. In conclusion, they express confidence in the success of the upcoming competition, urging collaboration and constructive dialogue among delegations to make the event impactful and memorable.`,
  },
  {
    id: 'myanmar',
    name: 'Mrs. Mya Mya Thet',
    position: 'Head of Delegation',
    country: 'Myanmar',
    flag: '/asean/flag/myanmar.webp',
    image: '/asean/focals/myamya.png',
    backgroundImage: '/asean/place/plmyanmar.png',
    description: `The speaker, representing Myanmar’s Department of Labour, expresses gratitude to WorldSkills Philippines for hosting the 1st Organizing Committee Meeting for the 14th WorldSkills ASEAN Competition and welcomes the ASEAN delegates. They highlight the value of previous competitions in improving training and skills assessment. The speaker emphasizes that skills competitions are vital for career exploration and lifelong learning, benefiting training centers, assessors, and employers. They also address challenges like AI and skilled labor mobility and stress the need for sustainable development in upgrading migrant workers' skills. Myanmar aims to participate in more skills areas this time. The speaker looks forward to a successful event in the Philippines.`,
  },
  {
    id: 'philippines',
    name: 'Mr. Vidal D. Villanueva III',
    position: 'Official Delegate',
    country: 'Philippines',
    flag: '/asean/flag/philippines.jpg',
    image: '/asean/focals/vidal.png',
    backgroundImage: '/asean/place/plphilippines.png',
    description: `Speech not Found.`,
  },
  {
    id: 'singapore',
    name: 'Ms. Low Khah Gek',
    position: 'Official Delegate',
    country: 'Singapore',
    flag: '/asean/flag/singapore.webp',
    image: '/asean/focals/low.png',
    backgroundImage: '/asean/place/plsingapore.png',
    description: `Representing Singapore, greets the ASEAN delegates and expresses gratitude to the Philippines for hosting the 1st Organizing Committee Meeting for the 14th ASEAN Skills Competition. They acknowledge the challenges posed by global uncertainty and stress the importance of regional cooperation and skills proficiency. The speaker emphasizes that the ASEAN Skills Competition is essential for promoting youth skills, fostering innovation, and encouraging cultural exchange. In conclusion, they thank the Philippines again and look forward to a productive meeting and an exciting competition.`,
  },
  {
    id: 'thailand',
    name: 'Mr. Phichet Tongpan',
    position: 'Official Delegate',
    country: 'Thailand',
    flag: '/asean/flag/thailand.webp',
    image: '/asean/focals/phichet.png',
    backgroundImage: '/asean/place/plthailand.png',
    description: `The speaker expresses gratitude for being in Manila and thanks WorldSkills Philippines and TESDA for hosting the 1st OCM of the 14th WorldSkills ASEAN Competition in 2025. They highlight WorldSkills ASEAN as the largest showcase of professional and technical skills in Southeast Asia. Reflecting on WorldSkills ASEAN 2023 in Singapore, the speaker emphasizes the importance of youth collaboration, knowledge exchange, and skill development to maintain a competitive workforce. In closing, they wish the delegates success and express gratitude for being part of the meeting, which promotes excellence and the development of highly skilled workers.`,
  },
  {
    id: 'vietnam',
    name: 'Mr. Nguyen Chi Truong',
    position: 'Head of Delegation',
    country: 'Vietnam',
    flag: '/asean/flag/vietnam.webp',
    image: '/asean/focals/truong.png',
    backgroundImage: '/asean/place/plvietnam.png',
    description: `Speech not Found.`,
  },
  ];
  
  // Use refs to store modal components
  const modals = ref([]);
  
  // Function to open a modal by ID
  const openModal = (id) => {
    console.log(`Opening Modal for: ${id}`);
    const modal = modals.value.find((m) => m.$props.id === `modal-${id}`);
    if (modal) {
      modal.openModal();
    } else {
      console.error(`Modal with ID "modal-${id}" not found.`);
    }
  };
  </script>
  
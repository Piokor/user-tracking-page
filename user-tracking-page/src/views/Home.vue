<template>
  <v-container>
    <v-row>
      <v-sheet rounded="lg" class="pa-5">
        <paragraph v-for="i in Array(paragraphsPerBlock).keys()" :index="i + 1" class="mb-5" />
        <div class="pa-10" ref="avatarElement" style="background-color: yellow">IMAGE</div>
        <paragraph
          v-for="i in Array(paragraphsPerBlock).keys()"
          :index="i + paragraphsPerBlock + 1"
          class="mb-5"
        />
      </v-sheet>
    </v-row>
  </v-container>
</template>

<script lang="ts" setup>
import Paragraph from '@/components/home/Paragraph.vue';
import { ref, onMounted, onUnmounted } from 'vue';

const paragraphsPerBlock = 10;
const avatarElement = ref(null);
const avatarWasDisplayed = ref(false);

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});

const handleScroll = e => {
  if (avatarWasDisplayed.value) return;

  if (isAvatarDisplayed()) {
    avatarWasDisplayed.value = true;
    console.log('AVATAR');
  }
};

const isAvatarDisplayed = () => {
  // Access the avatar DOM element and get the position
  const element = avatarElement.value;
  const rect = element.getBoundingClientRect();

  // Determine if top of avatar is at the bottom of the page
  const distanceToBottom = rect.top - window.innerHeight;
  return distanceToBottom < 0;
};
</script>

<template>
  <q-page class="q-pa-md q-px-lg">
    <div class="row items-start q-col-gutter-lg">
      <div
        v-for="video in videos"
        :key="video.id"
        class="col-12 col-sm-6 col-md-4 col-lg-3"
      >
        <video-component :video="video"></video-component>
      </div>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { Video } from 'components/models';
import VideoComponent from 'src/components/VideoComponent.vue';

defineOptions({
  name: 'IndexPage',
});

const videos = ref<Video[]>([
  {
    id: 1,
    title: 'Episode 1: I challenged everything',
    channel: 'Korean Podcast',
    channel_image: 'https://cdn.quasar.dev/img/avatar2.jpg',
    thumbnail_image: 'https://cdn.quasar.dev/img/parallax1.jpg',
    views: 12,
  },
  {
    id: 2,
    title: 'Episode 2: Discover the world',
    channel: 'Travel Adventures',
    channel_image: 'https://cdn.quasar.dev/img/avatar2.jpg',
    thumbnail_image: 'https://cdn.quasar.dev/img/parallax2.jpg',
    views: 34,
  },
  {
    id: 3,
    title: 'Cooking Masterclass: How to make pizza',
    channel: "Chef's Kitchen",
    channel_image: 'https://cdn.quasar.dev/img/avatar2.jpg',
    thumbnail_image: 'https://cdn.quasar.dev/img/mountains.jpg',
    views: 56,
  },
  {
    id: 4,
    title: 'Tech Talk: Latest gadgets and innovations',
    channel: 'TechByte',
    channel_image: 'https://cdn.quasar.dev/img/avatar2.jpg',
    thumbnail_image: 'https://cdn.quasar.dev/img/quasar.jpg',
    views: 78,
  },
  {
    id: 5,
    title: 'Fitness Tips: Stay healthy and fit',
    channel: 'FitFam',
    channel_image: 'https://cdn.quasar.dev/img/avatar2.jpg',
    thumbnail_image: 'https://cdn.quasar.dev/img/parallax2.jpg',
    views: 90,
  },
  {
    id: 6,
    title: "Gaming Fun: Let's play some games!",
    channel: "Gamer's Paradise",
    channel_image: 'https://cdn.quasar.dev/img/avatar2.jpg',
    thumbnail_image: 'https://cdn.quasar.dev/img/parallax1.jpg',
    views: 102,
  },
  {
    id: 7,
    title: "Fashion Trends: What's hot right now?",
    channel: 'Fashionista',
    channel_image: 'https://cdn.quasar.dev/img/avatar2.jpg',
    thumbnail_image: 'https://cdn.quasar.dev/img/quasar.jpg',
    views: 124,
  },
  {
    id: 8,
    title: 'DIY Crafts: Get creative with crafts',
    channel: 'Crafty Corner',
    channel_image: 'https://cdn.quasar.dev/img/avatar2.jpg',
    thumbnail_image: 'https://cdn.quasar.dev/img/mountains.jpg',
    views: 146,
  },
]);
</script>

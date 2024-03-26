<template>
  <q-card flat class="">
    <q-img :src="video.thumbnail_image" height="210px" fit="cover" />

    <q-card-section class="q-pl-none q-pt-none">
      <q-item class="q-pl-none">
        <q-item-section avatar>
          <q-avatar>
            <img :src="video.channel_image" />
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-h6">{{ video.title }}</q-item-label>
          <q-item-label>{{ video.channel }}</q-item-label>
          <q-item-label caption>{{ video.views }} Views</q-item-label>
        </q-item-section>
      </q-item>
    </q-card-section>
  </q-card>
</template>

<script setup lang="ts">
import { Video } from './models';

interface Props {
  video: Video;
}

withDefaults(defineProps<Props>(), {});
</script>

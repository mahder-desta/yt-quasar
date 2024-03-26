<template>
  <q-layout view="hHh Lpr lFf" class="bg-white">
    <q-header class="bg-white text-grey-8 q-py-xs" height-hint="58">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          class="text-dark"
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          v-if="!$q.screen.gt.xs"
        />

        <q-btn
          flat
          dense
          round
          class="text-dark"
          icon="menu"
          aria-label="Menu"
          @click="toggleMinState"
          v-if="$q.screen.gt.xs"
        />

        <q-btn flat dense no-caps class="q-ml-xs" v-if="$q.screen.gt.xs">
          <q-icon :name="fabYoutube" color="red" size="28px" />
          <q-toolbar-title shrink class="text-weight-bold">
            YouTube
          </q-toolbar-title>
        </q-btn>

        <q-space />

        <div class="YL__toolbar-input-container row no-wrap">
          <q-input
            dense
            outlined
            rounded
            v-model="search"
            placeholder="Search"
            class="bg-white col"
          />
          <q-btn
            class="YL__toolbar-input-btn"
            color="grey-3"
            text-color="grey-8"
            icon="search"
            unelevated
            rounded
          />
          <q-btn
            round
            dense
            flat
            color="grey-8 "
            style="right: 70px"
            icon="keyboard"
          />
        </div>
        <q-btn round dense flat color="grey-8 q-ml-xs" icon="mic" />

        <q-space />

        <div class="q-gutter-sm row items-center no-wrap">
          <q-btn round dense flat color="grey-8" icon="more_vert">
            <q-tooltip>More Actions</q-tooltip>
          </q-btn>

          <q-btn
            style="border: 1px solid; border-radius: 20px"
            flat
            class="q-px-md text-blue-8"
            v-if="$q.screen.gt.sm"
          >
            <q-avatar icon="account_circle" size="26px"> </q-avatar>
            User
            <q-tooltip>Account</q-tooltip>
          </q-btn>
          <q-btn
            round
            dense
            flat
            color="grey-8"
            icon="invert_colors"
            v-if="$q.screen.gt.sm"
          >
            <q-tooltip>Theme</q-tooltip>
          </q-btn>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      :mini="miniState"
      :mini-width="80"
      class=""
      :width="200"
      :breakpoint="667"
    >
      <q-scroll-area class="fit">
        <q-btn
          flat
          dense
          no-caps
          class="q-ml-sm q-mt-sm"
          v-if="!$q.screen.gt.xs"
        >
          <q-icon :name="fabYoutube" color="red" size="28px" />
          <q-toolbar-title shrink class="text-weight-bold">
            YouTube
          </q-toolbar-title>
        </q-btn>
        <q-list padding>
          <q-item clickable v-ripple>
            <q-item-section class="column justify-center" avatar>
              <q-icon name="home" class="self-center" />
              <span
                class="self-center text-caption text-weight-light"
                v-if="miniState && $q.screen.gt.xs"
                >Home</span
              >
            </q-item-section>

            <q-item-section> Home </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section class="column justify-center" avatar>
              <q-icon name="music_note" class="self-center" />
              <span
                class="text-center self-center text-caption text-weight-light"
                v-if="miniState && $q.screen.gt.xs"
                >Shorts</span
              >
            </q-item-section>

            <q-item-section> Shorts </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section class="column justify-center" avatar>
              <q-icon name="ondemand_video" class="self-center" />
              <span
                class="text-center self-center text-caption text-weight-light"
                v-if="miniState && $q.screen.gt.xs"
                >Tv</span
              >
            </q-item-section>

            <q-item-section> TV </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section class="column justify-center" avatar>
              <q-icon name="library_music" class="self-center" />
              <span
                class="text-center self-center text-caption text-weight-light"
                v-if="miniState && $q.screen.gt.xs"
                >Channels</span
              >
            </q-item-section>

            <q-item-section> Channels </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section class="column justify-center" avatar>
              <q-icon name="history" class="self-center" />
              <span
                class="text-center self-center text-caption text-weight-light"
                v-if="miniState && $q.screen.gt.xs"
                >History</span
              >
            </q-item-section>

            <q-item-section> History </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { fabYoutube } from '@quasar/extras/fontawesome-v6';

import { ref } from 'vue';

defineOptions({
  name: 'MainLayout',
});

const leftDrawerOpen = ref(false);

const miniState = ref(true);
const search = ref('');

function toggleMinState() {
  miniState.value = !miniState.value;
}

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>

<style lang="sass">
.YL

  &__toolbar-input-container
    min-width: 100px
    width: 55%
    position: relative

  &__toolbar-input-btn
    position: absolute
    right: 0
    top: 0
    bottom: 0
    border-style: solid
    border-width: 1px 1px 1px 0
    border-color: rgba(0,0,0,.24)
    max-width: 60px
    width: 100%


  &__drawer-footer-link
    color: inherit
    text-decoration: none
    font-weight: 500
    font-size: .75rem

    &:hover
      color: #000
</style>

<template>
  <q-page>
    <q-card class="q-mb-md">
      <q-input
        standout
        dense
        debounce="300"
        @click="$router.push('/menus')"
        placeholder="Add a song..."
        style="width: 100%"
      >
        <template #append>
          <q-icon name="search" />
        </template>
      </q-input>
    </q-card>

    <div
      v-if="banner && !$q.platform.is.capacitor"
      class="q-mb-md"
      style="width: 100%"
    >
      <q-banner inline-actions dense rounded class="text-white">
        <template #avatar>
          <q-icon name="shopping_bag" />
        </template>
        <div class="text-subtitle2 text-center">
          <!-- Yale Buttery Book is now available on the App Store! -->
        </div>
        <template #action>
          <q-btn flat label="Install" to="/install" />
          <q-btn flat icon="close" @click="banner = false" />
        </template>
      </q-banner>
    </div>

    <q-card class="q-mb-md">
      <q-card-section class="text-h5">Queue</q-card-section>
      <q-card-section>
        <SongCardList
          :songs="queue"
          :emptyMessage="{
            overline: 'Oops!',
            header: 'No Butteries Open',
            text: 'Maybe try snackpass :(',
          }"
        />
      </q-card-section>
    </q-card>
    <q-card>
      <q-card-section class="text-h5">Playlist</q-card-section>
      <q-card-section>
        <SongCardList
          :songs="playlist"
          :emptyMessage="{
            overline: 'Yay!',
            header: 'No Butteries Closed',
            text: 'Today is a good day!',
          }"
        />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
// import { useQuasar } from 'quasar';
// import { onBeforeRouteLeave } from 'vue-router';

const queue = ref([]);
const playlist = ref([]);

// startSync();

// async function pullRefresh(done: () => void): Promise<void> {
//   await refresh();
//   done();
// }

const banner = ref(true);

// --- App Visibility Toggles Sync ---
// const $q = useQuasar();
// watch(
//   () => $q.appVisible,
//   (val) => {
//     console.log(val ? 'App became visible' : 'App went in the background');
//     if (val) {
//       startSync();
//     } else {
//       stopSync();
//     }
//   }
// );

// --- Routing ---
// onBeforeRouteLeave(() => {
//   stopSync();
// });
</script>

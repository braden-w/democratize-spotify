<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <!-- <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        /> -->

        <q-btn
          class="text-h6 text-weight-light"
          no-caps
          flat
          to="/"
          icon="library_add"
          label="Democratize Spotify"
        />
        <q-avatar>
          <!-- TODO: <img src="../../public/Icon.png" alt="" /> -->
        </q-avatar>
        <!-- <q-btn
          v-if="$q.screen.gt.md"
          color="accent"
          icon="download"
          label="Add to Home Screen"
          @click="installDialog.open"
        />
        <q-btn v-else round flat icon="download" @click="installDialog.open" /> -->
        <q-space />
        <InstallDialog />
        <ReportDialog />
        <q-btn round flat icon="info" to="/about" />
        <!-- <q-btn
          v-if="$q.screen.lt.sm"
          icon="search"
          color="accent"
          to="/menus"
        />
        <q-btn
          v-else-if="$q.screen.lt.md"
          icon="search"
          color="accent"
          label="Menus"
          to="/menus"
        />
        <q-btn
          v-else
          icon="search"
          color="accent"
          label="Browse Menus"
          to="/menus"
        /> -->

        <q-toggle
          color="blue-grey-5"
          v-model="$q.dark.mode"
          @click="$q.dark.toggle()"
        >
        </q-toggle>
      </q-toolbar>
    </q-header>

    <!-- <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header>
          Navigation
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer> -->

    <q-page-container>
      <router-view />
      <div class="text-center">&copy; Buttery Book 2022</div>
      <q-page-sticky position="bottom-right" :offset="[18, 18]">
        <q-btn fab icon="campaign" @click="reportGeneral()" color="accent"
          >Add Song</q-btn
        >
      </q-page-sticky>
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
// import { useQuasar } from 'quasar';
// import InstallDialog from 'src/components/InstallDialog.vue';
// import ReportDialog from 'src/components/ReportDialog.vue';
// import { residentialColleges } from 'src/shared/butteries';

// const $q = useQuasar();
const reportGeneral = () => ({});
// function reportGeneral() {
//   $q.dialog({
//     component: ReportDialog,
//     componentProps: {
//       placeHolderCollege: residentialColleges[0],
//       placeHolderMessage: 'It would be great if...',
//     },
//   })
//     .onOk(() => {
//       console.log('OK');
//     })
//     .onCancel(() => {
//       console.log('Cancel');
//     })
//     .onDismiss(() => {
//       console.log('Called on OK or Cancel');
//     });
// }
</script>

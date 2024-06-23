<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar class="custom-toolbar">

        <q-btn-dropdown class="custom-dropdown" label="Aldi Kuncruk" dropdown-icon=" ">
          <q-list class="nav-list">
            <q-item clickable v-close-popup>
              <router-link to="/">
                <q-item-section>
                  <q-item-label style="color: var(--lightest-gray);">Cuaca</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas1">
                <q-item-section>
                  <q-item-label style="color: var(--lightest-gray);">Tugas 1</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas2">
                <q-item-section>
                  <q-item-label style="color: var(--lightest-gray);">Tugas 2</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas3">
                <q-item-section>
                  <q-item-label style="color: var(--lightest-gray);">Tugas 3</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas4">
                <q-item-section>
                  <q-item-label style="color: var(--lightest-gray);">Tugas 4</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas5">
                <q-item-section>
                  <q-item-label style="color: var(--lightest-gray);">Tugas 5</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas6">
                <q-item-section>
                  <q-item-label style="color: var(--lightest-gray);">Tugas 6</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas7">
                <q-item-section>
                  <q-item-label style="color: var(--lightest-gray);">Tugas 7</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view></router-view>
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  setup() {

  },
};
</script>

<style>
@import './assets/index.css';

.custom-toolbar {
  background-color: var(--dark-gray);
  color: var(--lightest-gray);
  text-decoration: none;
  border-bottom: 1px dotted var(--lightest-gray);
}

.custom-dropdown {
  background-color: var(--medium-gray);
  color: var(--lightest-gray);
  border: 1px dotted whitesmoke !important;
}

.nav-list {
  background-color: var(--dark-gray);
  color: var(--lightest-gray);
  border: 1px dotted whitesmoke;
}

.nav-list .q-item link {
  text-decoration: none;
}

.q-item-section {
  color: var(--light-gray) !important;
}
</style>

<template>
  <base-layout page-tile="All Memories">
    <template v-slot:actions-end>
      <ion-buttons router-link="/memories/add">
        <ion-icon slot="icon-only" :icon="add"></ion-icon>
      </ion-buttons>
    </template>
    <memories-list :memories="memories"></memories-list>
  </base-layout>
</template>

<script>
import MemoriesList from "../components/memories/MemoriesList.vue";
import { IonButtons, IonIcon } from "@ionic/vue";
import { add } from "ionicons/icons";
export default {
  name: "MemoriesPage",

  components: {
    MemoriesList,
    IonButtons,
    IonIcon,
  },
  data() {
    return { add };
  },
  computed: {
    memories() {
      return this.$store.getters.memories;
    },
  },
};
</script>

<style lang="scss" scoped></style>

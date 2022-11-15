<template>
  <base-layout
    :page-tile="loadedMemory ? loadedMemory.title : 'loading...'"
    page-default-back-link="/memories"
  >
    <h2 v-if="!loadedMemory">Could not find a memory for the given id.</h2>
    <memory-overview
      :title="loadedMemory.title"
      :image="loadedMemory.image"
      :description="loadedMemory.description"
    />
  </base-layout>
</template>

<script>
import MemoryOverview from "../components/memories/MemoriesOverView.vue";
export default {
  components: {
    MemoryOverview,
  },
  name: "VcrMobileMemoriesDetail",
  data() {
    return {
      memoryId: this.$route.params.id,
    };
  },
  computed: {
    loadedMemory() {
      return this.$store.getters.memory(this.memoryId);
    },
  },
};
</script>

<style lang="scss" scoped></style>

<template>
  <form class="ion-padding" @submit.prevent="submitForm">
    <ion-list>
      <ion-item>
        <ion-label position="floating"> Title </ion-label>
        <ion-input type="text" required v-model="enteredTitle"></ion-input>
      </ion-item>
      <ion-item>
        <ion-label position="floating"> Image Url </ion-label>
        <ion-input type="url" required v-model="enterdImageUrl"></ion-input>
      </ion-item>
      <ion-item>
        <ion-label position="floating"> Description </ion-label>
        <ion-textarea
          rows="5"
          required
          v-model="enterdDescription"
        ></ion-textarea>
      </ion-item>
    </ion-list>
    <ion-button type="submit" expand="full">Save</ion-button>
  </form>
</template>

<script>
import {
  IonList,
  IonItem,
  IonLabel,
  IonInput,
  IonTextarea,
  IonButton,
} from "@ionic/vue";
export default {
  name: "MyAppCreateMemoryForm",
  emits: ["save-memory"],
  components: {
    IonList,
    IonItem,
    IonLabel,
    IonInput,
    IonTextarea,
    IonButton,
  },
  data() {
    return {
      enteredTitle: "",
      enterdDescription: "",
      enterdImageUrl: "",
    };
  },

  mounted() {},

  methods: {
    submitForm() {
      const memoryData = {
        title: this.enteredTitle,
        imageUrl: this.enterdImageUrl,
        description: this.enterdDescription,
      };
      this.$emit("save-memory", memoryData);
    },
  },
};
</script>

<style lang="scss" scoped></style>

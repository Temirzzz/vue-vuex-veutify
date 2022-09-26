<template>
  <v-container>
    <PhotoForm v-if="photos.length < 11" @addPhoto="addPhoto" />
    <div v-else>Вы не можете добавить больше фотографий</div>
    <v-row>
      <Photo
        v-for="photo in $store.getters.getAllPhotos"
        v-bind:photo="photo"
      />
    </v-row>
    <PhotoDialog />
  </v-container>
</template>

<script>
import Photo from "@/components/photo/Photo.vue";
import PhotoForm from "@/components/photo/PhotoForm.vue";
import PhotoDialog from "@/components/photo/PhotoDialog.vue";

export default {
  components: { Photo, PhotoForm, PhotoDialog },
  data: () => ({
    photos: [],
  }),
  mounted() {
    this.$store.dispatch("fetchPhotos");
  },
  methods: {
    addPhoto(photo) {
      this.photos.push(photo);
    },
    openPhoto(photo) {
      this.currentPhoto = photo;
      this.dialogVisible = true;
    },
  },
};
</script>

<style lang="scss" scoped></style>

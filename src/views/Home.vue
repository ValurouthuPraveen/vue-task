<template>
  <div class="home">
    <file-upload :validExtensions="validExtensions" :validSizes="validSizes" :maxSizeAllowed="maxSizeAllowed" @fileUploaded="file = $event"></file-upload>
  </div>
</template>

<script>
import FileUpload from '../components/FileUpload.vue'

export default {
  name: "Home",
  data() {
    return {
      validExtensions: ['jpg','jpeg','png','doc','pdf','csv','bmp'],
      validSizes : ['5mb','10mb'],
      maxSizeAllowed: 300000,
      file:'',
    }
  },
  watch: {
    file(newValue) {
      console.log(newValue);
    }
  },
  components: {
    FileUpload,
  },
};
</script>

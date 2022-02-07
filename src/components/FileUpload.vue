<template>
  <div>
    <div>
      <b-alert
        :show="showWarning"
        :variant="variant"
        @dismissed="showWarning = false"
        dismissible
      >
        {{ warningText }}
      </b-alert>
    </div>
    <h2>File Upload</h2>

    <b-form-file v-model="file2" class="mt-3" plain></b-form-file>

    <b-button variant="primary" @click="uploadFile()">Upload</b-button>
  </div>
</template>

<script>
export default {
  name: "FileUpload",
  props: ["validExtensions", "validSizes", "maxSizeAllowed"],
  data() {
    return {
      file2: null,
      fileExtension: "",
      sizeOfFile: "",
      showWarning: false,
      warningText: "",
      variant: 'danger',
    };
  },
  methods: {
    uploadFile() {
      if (!this.file2) {
        this.showWarning = true;
        this.warningText = 'Please choose a file to continue';
        this.variant = 'danger';
      } else {
        const ext = this.getExtension();
        const size = this.formatBytes(this.file2.size);
        if (
          this.validExtensions.includes(ext) &&
          this.file2.size <= this.maxSizeAllowed &&
          size != "0 Bytes"
        ) {
          this.$emit("fileUploaded", "file uploaded successfully");
          this.variant = 'success';
          this.warningText = 'File Uploaded Successfully';
          this.showWarning = true;
        }
        if (!this.validExtensions.includes(ext)) {
          this.warningText = `This (${this.getExtension()}) file type is not supported.
            You can only upload file with .jpg, .jpeg, .png extension`;
          this.showWarning = true;
          this.variant = 'warning';
        }
        if (this.file2.size > this.maxSizeAllowed) {
          this.warningText = `The file size (${size}) is too large.
            You can only upload file with size below 3MB`;
          this.showWarning = true;
          this.variant = 'warning';
        }
        if (size == "0 Bytes") {
          this.warningText = `You cannot upload empty files`;
          this.showWarning = true;
          this.variant = 'warning';
        }
      }
    },
    getExtension() {
      const ext = this.file2.name.split(".");
      this.fileExtension = ext.pop();
      return this.fileExtension;
    },
    formatBytes(bytes, decimals = 2) {
      if (bytes === 0) return "0 Bytes";

      const k = 1024;
      const dm = decimals < 0 ? 0 : decimals;
      const sizes = ["Bytes", "KB", "MB", "GB", "TB", "PB", "EB", "ZB", "YB"];

      const i = Math.floor(Math.log(bytes) / Math.log(k));

      return parseFloat((bytes / Math.pow(k, i)).toFixed(dm)) + " " + sizes[i];
    },
  },
};
</script>

<style scoped>

</style>

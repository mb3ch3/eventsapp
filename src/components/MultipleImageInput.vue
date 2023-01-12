<template>
  <div
    class="base-image-input"
    :style="{ 'background-image': `url(${imageData})`,'backgroundSize' : '30%', 'background-repeat': 'no-repeat' }"
    @click="chooseImage"
  >
    <span v-if="!imageData" class="placeholder">
      <div class="wording">
          <i class="ri-add-line ri-2x"></i>
        Upload additional images
        </div
    ></span>

    <input
        multiple
      class="file-input"
      ref="fileInput"
      type="file"
      @input="onSelectFile"
    />
  </div>
</template>

  <script>
export default {
  data() {
    return {
      imageData: null,
    };
  },
  methods: {
    chooseImage() {
      this.$refs.fileInput.click();
    },
    onSelectFile() {
      const input = this.$refs.fileInput;
      const files = input.files;
      if (files && files[0]) {
        const reader = new FileReader();
        reader.onload = (e) => {
          this.imageData = e.target.result;
        };
        reader.readAsDataURL(files[0]);
        this.$emit("input", files[0]);
      }
    },
  },
};
</script>
<style scoped>
.wording{
    display: flex;
    flex-direction: column;
    font-size:smaller;
    justify-content: center;
    align-items: center;
}
.base-image-input {
    
  background: transparent;
  display: block;
  width: 100%;
  height: 200px;
  cursor: pointer;
  background-size: cover;
  background-position: center center;
  /* border: 1px solid lightsteelblue; */
  /* border-radius: 0 50px 30px 0; */
  /* background: red; */
}
.placeholder {
  background: transparent;
  /* background: green; */
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #333;
  font-size: 18px;
  font-family: Helvetica;
  /* border-radius: 0 20px 20px 0 */
}
.placeholder:hover {
  color: black;
  font-weight: 900;
  background: white;
}
.file-input {
  display: none;
}
</style>
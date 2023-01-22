<template>
  <div class="form">
    <form v-on:submit.prevent method="post" v-on:submit="showdata" action="http://localhost:3000/createEvent">
      <div class="field">
        <div class="field-icon">
          <i class="ri-edit-line"></i>
            </div>
            <div class="field-input">
              <input
                type="text"
                v-model="body.eventname"
                name="eventname"
                placeholder="Enter event name"
              />
            </div>
      </div>
      <div class="top-form">
        <div class="top-left">
          <div class="field">
            <div class="field-icon">
              <i class="ri-user-line"></i>
            </div>
            <div class="field-input">
              <input
                type="text"
                v-model="body.organizer"
                name="organizer"
                placeholder="Organizer's name"
              />
            </div>
          </div>
          <div class="field">
            <div class="field-icon">
              <i class="ri-list-unordered"></i>
            </div>
            <div class="field-input custom-select">
              <select v-model="body.category" name="category" id="">
                <option value="" disabled selected>Pick a category</option>
                <option value="cat1">cat1</option>
                <option value="cat2">cat2</option>
                <option value="cat3">cat3</option>
                <option value="cat4">cat4</option>
                <option value="cat5">cat5</option>
              </select>
            </div>
          </div>
        </div>
        <div class="top-right">
          <div class="field">
            <div class="field-icon">
              <i class="ri-map-pin-2-line"></i>
            </div>
            <div class="field-input">
              <input
                type="text"
                v-model="body.location"
                name="location"
                placeholder="location"
              />
            </div>
          </div>
          <div class="field">
            <div class="field-icon">
              <i class="ri-calendar-event-fill"></i>
            </div>
            <div class="field-input">
              <input
                type="date"
                v-model="body.date"
                name="date"
                placeholder="pick date"
              />
            </div>
          </div>
        </div>
      </div>
      <div class="bottom-form">
        <div class="field">
          <div class="field-icon">
            <i class="ri-double-quotes-l"></i>
          </div>
          <div class="field-input">
            <input
              type="text"
              v-model="body.description"
              name="description"
              placeholder="Give us a description"
            />
          </div>
        </div>
      </div>
      <!-- <div class="drop-images">
        <div class="dropbox">
          <img :src="imageData" alt="" />
        </div>
        <div class="dropbox">
          <img :src="imageData" alt="" />
        </div>
      </div> -->

      <div class="lower-form">
        <div class="field3">
          <div class="field-icon">
            <i class="ri-image-add-fill"></i>
          </div>
          <div class="dropbox">
            <BaseImageInput v-model="body.imageFile" />
          </div>
        </div>

        <div class="field3">
          <div class="field-icon">
            <i class="ri-image-add-fill"></i>
          </div>
          <MultipleImageInput v-model="body.imageFile2" />
        </div>
      </div>
      <div class="lower-form2">
        <div class="field2">
          <div class="field-icon">
            <i class="ri-filter-3-line"></i>
          </div>
          <div class="field-input2">
            <label for="">Do you want a feature</label>
            <input
              type="checkbox"
              name="featuring"
              v-on:change="featureselect"
            />
          </div>
        </div>
        <div class="field">
          <div class="field-icon">
            <i class="ri-price-tag-3-line"></i>
          </div>
          <div class="field-input">
            <input
              type="number"
              v-model="body.price"
              name="price"
              placeholder="price"
            />
          </div>
        </div>
      </div>
      <div class="cent">
        <button type="submit">Register</button>
      </div>
    </form>
  </div>
</template>



<script>
import BaseImageInput from "../components/BaseImageInput.vue";
import MultipleImageInput from "../components/MultipleImageInput.vue";
/* eslint-disable */
import axios from "axios";
const headers = {
  "Content-Type": "application/json",
};

export default {
  components: { BaseImageInput, MultipleImageInput },
  data() {
    return {
      body: {
        organizer: "",
        eventname:"",
        category: "",
        description: "",
        location: "",
        date: "",
        featuring: "",
        price: "",
        imageFile: "",
        imageFile2: "",
      },
      main: "",
      subs: [],
      
    };
  },
  methods: {
    featureselect() {
      this.body.featuring = !this.body.featuring;
    },
    showdata() {
      axios({
        method: "post",
        url: "http://localhost:3000/createEvent",
        data: this.$data.body,
        headers: headers,
      }) .then((success) => {
        console.log(success);
      }) .catch((err)=>{
        console.log(err);
      })
      console.log(this.$data.body);
    },
  },
};
</script>

<style scoped>
.form {
  max-width: 75%;
  margin-inline: auto;
  /* background: yellow; */
  margin-top: 30px;
  padding: 30px;
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: auto auto auto auto auto;
}
.top-form {
  display: grid;
  grid-template-rows: auto;
  grid-template-columns: auto auto;
  /* background: green; */
  justify-content: stretch;
  align-items: center;
  grid-column-gap: 10px;
}

.field {
  /* background: blue; */
  display: grid;
  grid-template-columns: 0.5fr 3fr;
  height: 6vh;
  border: 1px solid lightsteelblue;
  border-radius: 10px;
  align-items: center;
  padding-right: 8px;
}
.field3 {
  /* background: blue; */
  display: grid;
  grid-template-columns: 0.5fr 3fr;
  height: fit-content;
  border: 1px solid lightsteelblue;
  border-radius: 10px;
  align-items: center;
  padding: 0 5px 0 0;
}
.field2 {
  /* background: blue; */
  display: grid;
  grid-template-columns: 0.5fr 3fr;
  height: 6vh;
  /* border: 1px solid lightsteelblue; */
  border-radius: 10px;
  align-items: center;
  padding-right: 8px;
}
.field-icon {
  background: #b0c4de40;
  border-radius: 10px 0 0 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}
.field-input input {
  width: 100%;
  outline: none;
  border: none;
  padding-left: 8px;
}
.field-input select {
  width: 100%;
  outline: none;
  border: none;
  padding-left: 8px;
}
.bottom-form {
  margin-top: 15px;
}
.bottom-form .field {
  /* background: red; */
  height: 150px;
  align-items: flex-start;
}
.bottom-form .field .field-input input {
  /* background: orange; */
  margin-top: 10px;
  /* height: 130px; */
}
.lower-form {
  margin-top: 15px;
  display: grid;
  grid-template-columns: 2fr 5fr;
  grid-template-rows: auto;
  grid-column-gap: 10px;
  height: 200px;
}
.lower-form2 {
  margin-top: 15px;
  display: grid;
  grid-template-columns: 2fr 2fr;
  grid-template-rows: auto;
  grid-column-gap: 10px;
  justify-content: space-between;
}

.field-input2 {
  width: 100%;
  outline: none;
  border: none;
  padding-left: 8px;
  justify-content: space-between;
  align-items: center;
  display: flex;
}

label {
  font-size: smaller;
  /* color: red; */
}
button {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px;
  text-align: center;
  font-size: larger;
  font-family: "DM Serif Display", serif;
  text-transform: capitalize;
  border: 0.75px solid lightsteelblue;
  width: 20vw;
  margin-inline: auto;
  background: linear-gradient(to right, #2a2a72, #009ffd);
  color: white;
  font-size: medium;
}
.cent {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 23px;
}
.dropbox {
  overflow: hidden;
  /* outline: 2px dashed grey; the dash box */
  outline-offset: -10px;
  background: #fff;
  color: dimgray;
  /* padding: 10px 10px; */
  min-height: 200px; /* minimum height */
  position: relative;
  cursor: pointer;
}

.input-file {
  opacity: 0; /* invisible but it's there! */
  height: 200px;
  position: absolute;
  cursor: pointer;
}

.dropbox:hover {
  background: #b0c4de40; /* when mouse over to the drop zone, change color */
}

.dropbox p {
  font-size: 1.2em;
  text-align: center;
  padding: 50px 0;
}
.drop-images {
  display: grid;
  grid-template-columns: 1fr 2fr;
  margin: 20px 0;
}
/* input[type="date"]::-webkit-datetime-edit, input[type="date"]::-webkit-inner-spin-button, input[type="date"]::-webkit-clear-button {
  color: #fff;
  position: relative;
}

input[type="date"]::-webkit-datetime-edit-year-field{
  position: absolute !important;
  border-left:1px solid #8c8c8c;
  padding: 2px;
  margin: 0 2px;

  color:#000;
  left: 56px;
}

input[type="date"]::-webkit-datetime-edit-month-field{
  position: absolute !important;
  border-left:1px solid #8c8c8c;
  padding: 2px;
  margin: 0 2px;
  color:#000;
  left: 26px;
}


input[type="date"]::-webkit-datetime-edit-day-field{
  position: absolute !important;
  color:#000;
  padding: 2px;
  margin: 0 2px;

  left: 4px;
  
} */
</style>
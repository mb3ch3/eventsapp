<template>
  <div class="form">
    <form action="" method="post">
      <div class="top-form">
        <div class="top-left">
          <div class="field">
            <div class="field-icon">
              <i class="ri-user-line"></i>
            </div>
            <div class="field-input">
              <input type="text" placeholder="Organizer's name" />
            </div>
          </div>
          <div class="field">
            <div class="field-icon">
              <i class="ri-list-unordered"></i>
            </div>
            <div class="field-input">
              <select name="category" id="">
                <option value="cat1">cat1</option>
                <option value="cat1">cat1</option>
                <option value="cat1">cat1</option>
                <option value="cat1">cat1</option>
                <option value="cat1">cat1</option>
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
              <input type="text" placeholder="location" />
            </div>
          </div>
          <div class="field">
            <div class="field-icon">
              <i class="ri-calendar-event-fill"></i>
            </div>
            <div class="field-input">
              <input type="date" placeholder="pick date" />
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
            <input type="text" placeholder="Give us a description" />
          </div>
        </div>
      </div>
      <div class="lower-form">
        <div class="field">
          <div class="field-icon">
            <i class="ri-image-add-fill"></i>
          </div>
          <div class="field-input">
            <input type="file" placeholder="upload poster image" />
          </div>
        </div>
        <div class="field">
          <div class="field-icon">
            <i class="ri-image-add-fill"></i>
          </div>
          <div class="field-input">
            <input type="file" multiple placeholder="upload poster image" />
          </div>
        </div>
      </div>
      <div class="lower-form2">
        <div class="field2">
          <div class="field-icon">
            <i class="ri-filter-3-line"></i>
          </div>
          <div class="field-input2">
            <label for="">Do you want a feature</label>
            <input type="checkbox" />
          </div>
        </div>
        <div class="field">
          <div class="field-icon">
            <i class="ri-price-tag-3-line"></i>
          </div>
          <div class="field-input">
            <input type="number" placeholder="price" />
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
//name, category,description, main image, other images, location, date, time,
export default {};
</script>

<style>
.form {
  max-width: 75%;
  margin-inline: auto;
  /* background: yellow; */
  margin-top: 30px;
  padding: 30px;
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: auto auto auto auto;
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
  grid-template-columns: 1fr 2fr;
  grid-template-rows: auto;
  grid-column-gap: 10px;
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
.cent{
    display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 23px;
}
</style>
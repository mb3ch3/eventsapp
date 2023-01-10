<template>
  <div class="home">
    <section class="hero">
      <div class="featured">top Featured event</div>
      <div class="featured-details">
        <div class="featured-date">30th January, 2023</div>
        <div class="featured-title">
          Kishash kwa Bash: Bashment volume 1, 2023
        </div>
        <div class="featured-location">Fogo gaucho, Westlands</div>
        <div class="featured-desc">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Earum esse
          voluptate aspernatur perspiciatis ducimus sapiente doloribus excepturi
          rem, perferendis modi? Soluta animi unde architecto ipsam aliquam
          tenetur dicta modi ipsum.
        </div>
      </div>
    </section>
    <EventList />
    <EventReg />
    <EventCat />
  </div>
</template>
<script>
/* eslint-disable */
import EventReg from "@/components/EventReg.vue";
import EventList from "@/components/EventList.vue";
import EventCat from "../components/EventCat.vue";
export default {
  name: "home",
  components: {
    EventList,
    EventCat,
    EventReg,
  },
  methods: {
    ghg() {
      axios.get('http://localhost:3000/createEvent').then((res)=>{
        console.log(res);
      })
    },
  },
  mounted() {
    this.ghg();
  },
};
</script>
<style lang="scss" scoped>
.hero {
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: 1fr 4fr 1fr;
  background-image: url("https://teamorange.in/wp-content/uploads/2017/01/event-management-blog-1-performance.jpg");
  // background-image: url('https://cdn.pixabay.com/photo/2017/12/08/11/53/event-party-3005668__340.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  height: 400px;
}
.featured {
  background-blend-mode: hue;
  background: white;
  margin: 20px 0 0 6.3rem;
  padding: 10px;
  width: max-content;
  text-transform: uppercase;
  font-weight: bold;
  font-size: small;
  // font-family: 'DM Serif Display', serif;
  font-family: "Questrial", sans-serif;
  letter-spacing: 1px;
  color: black;
  display: flex;
  justify-content: center;
  align-items: center;
}
.featured-details {
  // background: red;
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: 0.5fr auto auto 1fr;
  grid-row-gap: 5px;
  width: 80vw;
  margin: 0 0 0 6.3rem;
}
.featured-date {
  font-family: "Questrial", sans-serif;
  color: white;
  background: black;
  padding: 10px;
  max-width: 10rem;
  text-transform: capitalize;
}
.featured-title {
  font-family: "DM Serif Display", serif;
  font-size: 3.2rem;
  color: black;
  padding: 0 10px;
  background: white;
  background-blend-mode: hue;
  width: fit-content;
  text-transform: capitalize;
}
.featured-location {
  font-family: "Questrial", sans-serif;
  color: aliceblue;
  background: black;
  padding: 10px;
  width: fit-content;
  text-transform: capitalize;
  font-weight: bold;
}
.featured-desc {
  font-family: "Questrial", sans-serif;
  color: white;
  // background: white;
  padding: 10px;
  width: fit-content;
  text-transform: capitalize;
}
</style>
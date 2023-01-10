<template>
  <div class="events">
    <h2 class="events-header">Check out other featured events</h2>
    <div class="error-msg" v-if="feat < 1">
      no featured events at the moment
    </div>
    <div v-else class="events-list">
      <div v-for="event in events" :key="event.id" class="event">
        <div v-if="event.featured">
          <router-link :to="'/event/' + event.id">
            <EventCard :event="event" />
          </router-link>
        </div>

        <!-- <div v-else>hhhdhsdidsi</div> -->
      </div>
    </div>
    <div class="more">Explore more <i class="ri-arrow-down-line"></i></div>
  </div>
</template>
  <script>
import EventCard from "../components/EventCard.vue";
/* eslint-disable */
export default {
  name: "eventlist",
  components: {
    EventCard,
  },
  data() {
    return {
      feat: 0,
      event: {},
      events: [
        {
          id: 1,
          featured: true,
          name: "Charity Ball",
          category: "Fundraising",
          description:
            "Spend an elegant night of dinner and dancing with us as we raise money for our new rescue farm.",
          featuredImage:
            "https://cdn.pixabay.com/photo/2017/12/08/11/53/event-party-3005668__340.jpg",
          images: [
            "https://placekitten.com/500/500",
            "https://placekitten.com/500/500",
            "https://placekitten.com/500/500",
          ],
          location: "1234 Fancy Ave",
          date: "31-01-2023",
          time: "11:30",
        },
        {
          id: 2,
          featured: true,
          name: "Kishash kwa Bash: Bashment volume 1, 2023",
          category: "Party",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage:
            "https://teamorange.in/wp-content/uploads/2017/01/event-management-blog-1-performance.jpg",
          images: ["https://placekitten.com/500/500"],
          location: "Fogo Gaucho, Westlands",
          date: "30-01-2023",
          time: "18:00",
        },
        {
          id: 3,
          featured: true,
          name: "Charity Ball",
          category: "Fundraising",
          description:
            "Spend an elegant night of dinner and dancing with us as we raise money for our new rescue farm.",
          featuredImage:
            "https://cdn.pixabay.com/photo/2017/12/08/11/53/event-party-3005668__340.jpg",
          images: [
            "https://placekitten.com/500/500",
            "https://placekitten.com/500/500",
            "https://placekitten.com/500/500",
          ],
          location: "1234 Fancy Ave",
          date: "31-01-2023",
          time: "11:30",
        },
        {
          id: 4,
          featured: true,
          name: "Charity Ball",
          category: "Fundraising",
          description:
            "Spend an elegant night of dinner and dancing with us as we raise money for our new rescue farm.",
          featuredImage:
            "https://cdn.pixabay.com/photo/2017/12/08/11/53/event-party-3005668__340.jpg",
          images: [
            "https://placekitten.com/500/500",
            "https://placekitten.com/500/500",
            "https://placekitten.com/500/500",
          ],
          location: "1234 Fancy Ave",
          date: "31-01-2023",
          time: "11:30",
        },
        {
          id: 5,
          featured: true,
          name: "Kishash kwa Bash: Bashment volume 1, 2023",
          category: "Party",
          description:
            "Come to our donation drive to help us replenish our stock of pet food, toys, bedding, etc. We will have live bands, games, food trucks, and much more.",
          featuredImage:
            "https://teamorange.in/wp-content/uploads/2017/01/event-management-blog-1-performance.jpg",
          images: ["https://placekitten.com/500/500"],
          location: "Fogo Gaucho, Westlands",
          date: "30-01-2023",
          time: "18:00",
        },
      ],
    };
  },
  mounted() {
    var tt = this.events.filter(function (elem) {
      if (elem.featured == true) return elem.id;
    });
    this.feat = tt.length
    console.log(this.feat);
  },
};
</script>
  <style lang="scss" scoped>
.events {
  // background: red;
  margin: 0 6.5rem;
}
.events-header {
  padding-top: 1rem;
  padding-bottom: 1rem;
  text-align: center;
  font-size: 27px;
  font-family: "DM Serif Display", serif;
  text-transform: capitalize;
  color: black;
}
.events-list {
  // display: grid;
  // justify-content: flex-start;
  // grid-template-columns: 1fr 1fr 1fr;
  // grid-template-rows: auto;
  // grid-column-gap: 20px;
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}
.more {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  margin: 20px;
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
.error-msg {
  font-weight: bold;
  font-family: "Questrial", sans-serif;
  text-transform: capitalize;
  text-align: center;
  padding: 50px 10px;
}
</style>
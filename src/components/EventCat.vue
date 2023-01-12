<template>
  <div class="categories">
    <div class="cat-header">Browse various event categories</div>
    <div class="cat-list">
      <div v-for="category in categories" :key="category.id" class="cat" :class="isactive && category.field == selected_category ? 'active': ''" @click="showselected(category.field)">
        {{ category.field }}
      </div>
    </div>
    <div class="error-msg" v-if="events.length < 1">
            no events at the moment
        </div>
    <div v-else class="events-list">
      <div v-for="event in events" :event="event" :key="event.id" class="event">
        
        <div v-if="event.category.toLocaleLowerCase() === selected_category">
            <router-link :to="'/event/' + event.id">
              <EventCard :event="event" />
            </router-link>
        </div>
        <div v-if="selected_category === 'all'">
            <router-link :to="'/event/' + event.id">
              <EventCard :event="event" />
            </router-link>
        </div>
        <div v-if="selected_category === 'featured' && event.featured === true">
            <router-link :to="'/event/' + event.id">
              <EventCard :event="event" />
            </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import EventCard from "./EventCard.vue";
export default {
  name: "EventCat",
  components: {
    EventCard,
  },
  data() {
    return {
        isactive:'',
        selected_category: 'all',
        category: '',
      categories: [
        {
          id: 1,
          field: "all",
        },
        {
          id: 2,
          field: "featured",
        },
        {
          id: 3,
          field: "education",
        },
        {
          id: 4,
          field: "sports",
        },
        {
          id: 5,
          field: "music",
        },
        {
          id: 6,
          field: "food",
        },
        {
          id: 7,
          field: "travel",
        },
        {
          id: 8,
          field: "fundraising",
        },
      ],
      events: [
      {
          id: 1,
          featured: false,
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
      ],
    };
  },
  methods:{
    showselected(selected){
        this.selected_category = selected
        console.log(this.selected_category)
        this.isactive = true
    }
  }
};
</script>

<style scoped>
.categories {
  background: #b0c4de30;
  padding: 0 6.5rem;
}
.cat-header {
  padding-top: 1rem;
  padding-bottom: 1rem;
  text-align: left;
  font-size: 27px;
  font-family: "DM Serif Display", serif;
  text-transform: capitalize;
  color: black;
}
.cat-list {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  gap: 20px;
  flex-wrap: wrap;
  margin-bottom: 20px;
}
.cat {
  min-width: 7rem;
  font-family: "Questrial", sans-serif;
  color: black;
  background: white;
  padding: 6px;
  width: fit-content;
  text-transform: capitalize;
  text-align: center;
}
.events-list {
  /* display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: auto;
  grid-column-gap: 20px; */
  display: flex;
  gap: 20px;
  margin-bottom: 20px;
  padding-bottom: 20px;
}

.active{
  background: linear-gradient(to right,#2A2A72,#009FFD);
  color: white;
}
.error-msg{
    font-weight: bold;
  font-family: "Questrial", sans-serif;
  text-transform: capitalize;
  text-align: center;
  padding: 50px 10px ;

}
</style>
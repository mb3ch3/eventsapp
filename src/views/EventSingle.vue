<template>
  <div class="event-single">
    <div class="left-side">
      <div class="images">
        <div class="main-image">
          <img :src="event.featuredImage" alt="" />
        </div>
        <div class="venue-images">
          <div
            v-for="image in event.images"
            :key="image.id"
            class="venue-image"
          >
            <img :src="image" :alt="event.name" />
          </div>
        </div>
      </div>
      <div class="loc-n-rev">
        <div class="location">
          <div class="loc-title">Location:</div>
          <div class="mapouter">
            <div class="gmap_canvas">
              <iframe
                width="100%"
                height="250"
                id="gmap_canvas"
                src="https://maps.google.com/maps?q=nairobi&t=&z=13&ie=UTF8&iwloc=&output=embed"
                frameborder="0"
                scrolling="no"
                marginheight="0"
                marginwidth="0"
              ></iframe>
              <a href="https://www.embedgooglemap.net"></a>
            </div>
          </div>
        </div>
        <div class="reviews">
          <div class="loc-title">Reviews:</div>
          <div class="review">
            <div class="prof-name">Young stunna</div>
            <div>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Cum, recusandae, asperiores impedit, qui tempore minima ipsam dolorem a sint quam porro officia vel ea molestias est laudantium quisquam blanditiis veritatis?</div>
          </div>
          <div class="review">
            <div class="prof-name">Young stunna</div>
            <div>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Saepe iste minus ipsa! Rem dolorem eaque non iusto quibusdam odio numquam beatae, aliquam odit facere ut iure quis quod totam blanditiis.
              Lorem ipsum, dolor sit amet consectetur adipisicing elit. Cum, recusandae, asperiores impedit, qui tempore minima ipsam dolorem a sint quam porro officia vel ea molestias est laudantium quisquam blanditiis veritatis?</div>
          </div>
          <div class="review">
            <div class="prof-name">Young stunna</div>
            <div>Lorem minima ipsam dolorem a sint quam porro officia vel ea molestias est laudantium quisquam blanditiis veritatis?</div>
          </div>
        </div>
      </div>
    </div>
    <div class="right-side">
      <div class="summary">
        <div class="event-name">{{ event.name }}</div>
        <div class="event-date">{{ event.date }}</div>
        <div class="event-time">{{ event.time }}</div>
        <div class="price">kes: 230</div>
      </div>
      <div class="get-ticket">Purchase ticket</div>
      <div class="description">{{ event.description }}</div>
      <div class="collapsibles">
        <div class="col-item" @click="showhidden">
          <div>host</div>
          <div><i class="ri-arrow-down-s-line"></i></div>
        </div>
        <div :class="can_see_host ? 'opened' : 'closed'">
          <b>the host name </b>
          <br>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ipsa vel aperiam ullam quod unde quia obcaecati et iure similique, facere non rem laborum vero quis provident deleniti illum vitae sunt?
        </div>
        <div class="col-item" @click="showhidden1">
          <div>venue</div>
          <div><i class="ri-arrow-down-s-line"></i></div>
        </div>
        <div :class="can_see_venue ? 'opened' : 'closed'">
          <b>the venue name</b>
          <br>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ipsa vel aperiam ullam quod unde quia obcaecati et iure similique, facere non rem laborum vero quis provident deleniti illum vitae sunt?
        </div>
        <div class="col-item" @click="showhidden2">
          <div>refund policy</div>
          <div><i class="ri-arrow-down-s-line"></i></div>
        </div>
      </div>
      <div :class="can_see_pol ? 'opened' : 'closed'" style="padding-left:10px">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Adipisci quos
        hic inventore cumque. Possimus amet animi, odit consectetur assumenda at
        et ut! Quisquam aliquid, expedita numquam maxime laborum provident
        cupiditate.
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Vel dolorem debitis doloremque tempora ducimus nemo fuga officia consequatur totam earum atque porro et sint, accusamus omnis ullam. Saepe, ab architecto.
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem veniam natus sunt provident minima aliquid, velit optio ad alias nisi animi architecto rerum? Dolores soluta, quis omnis laboriosam ducimus quo?
      </div>
    </div>
  </div>
</template>
  <script>
export default {
  name: "EventSingle",
  data() {
    return {
      can_see_host: false,
      can_see_venue: false,
      can_see_pol: false,
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
          images: ["https://placekitten.com/500/500","https://placekitten.com/500/500","https://placekitten.com/500/500"],
          location: "Fogo Gaucho, Westlands",
          date: "30-01-2023",
          time: "18:00",
        },
      ],
      event: {},
    };
  },
  created() {
    const ID = Number(this.$route.params.id);
    let event = this.events.find((event) => event.id === ID);
    this.event = event;
  },
  methods: {
    showhidden() {
      this.can_see_host = !this.can_see_host;
    },
    showhidden1() {
      this.can_see_venue = !this.can_see_venue;
    },
    showhidden2() {
      this.can_see_pol = !this.can_see_pol;
    },
  },
};
</script>
<style scoped>
.mapouter {
  position: relative;
  text-align: right;
  height: 250px;
  width: 100%;
}
.gmap_canvas {
  overflow: hidden;
  background: none !important;
  height: 250px;
  width: 100%;
}
.event-single {
  display: grid;
  grid-template-columns: 3fr 2fr;
  grid-template-rows: auto;
  padding: 20px 6.5rem;
}
.left-side {
  display: grid;
  grid-template-rows: auto auto;
  grid-template-columns: auto;
}
.images {
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: auto auto;
}
.main-image {
  width: 100%;
  aspect-ratio: 2/35/1;
}
.venue-images {
  display: flex;
  justify-content: space-between;
  gap: 15px;
}
.venue-image {
  width: 100%; /* or any custom size */
    height: 100%; 
    object-fit: contain;
}
.loc-n-rev {
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: auto auto;
  justify-content: flex-start;
}
.location {
  margin-top: 30px;
}
.loc-title{
  font-size: larger;
  font-weight: bold;
  padding: 10px 0;
  font-family: "Questrial", sans-serif;

}
.reviews {
  margin-top: 30px;
}
.review{
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: auto auto;
  background: #b0c4de05;
  border: #4682b420 0.5px solid;
  padding: 13px;
  margin: 10px 0;
  box-shadow: 5px 3px 5px 1px #77889920;
}
.prof-name{
  font-size: medium;
  font-weight: bold;
  color: black;
  text-decoration: underline;
  font-family: "DM Serif Display", serif;

}
.review div:nth-child(2){
  padding-left: 10px;
  font-family: "Questrial", sans-serif;
  color: black;
}
.right-side {
  display: flex;
  flex-direction: column;
  padding-left: 20px;
}
.summary {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.event-name {
  text-align: center;
  font-size: 27px;
  font-family: "DM Serif Display", serif;
  text-transform: capitalize;
  color: black;
}
.event-date {
  font-family: "Questrial", sans-serif;
  color: black;
  border-bottom: steelblue 0.5px solid;
  padding: 6px;
  width: 20rem;
  text-transform: capitalize;
}
.event-time {
  font-family: "Questrial", sans-serif;
  color: black;
  border-bottom: steelblue 0.5px solid;
  padding: 6px;
  width: 20rem;
  text-transform: capitalize;
}
.price {
  font-family: "Questrial", sans-serif;
  color: black;
  border-bottom: black 0.5px solid;
  padding: 6px;
  width: 20rem;
  text-transform: uppercase;
  font-weight: bolder;
}
.get-ticket {
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
.description {
  font-family: "Questrial", sans-serif;
  color: black;
  padding: 10px;
  width: fit-content;
  text-transform: capitalize;
}
.collapsibles {
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: auto auto auto auto auto auto;
  padding-inline: 10px;
}
.col-item {
  font-family: "Questrial", sans-serif;
  color: white;
  background: black;
  padding: 6px;
  width: 100%;
  text-transform: capitalize;
  float: right;
  border-bottom: 2px solid white;
  display: flex;
  justify-content: space-between;
}
.opened {
  display: block;
  animation: slidedown 0.3s ease-out;
  overflow: hidden;
}
.closed {
  display: none;
  animation: slideup 0.3s ease-out;
}
.opened,.closed{
  font-family: "Questrial", sans-serif;
  width: 100%;
  margin-bottom: 10px;
}
@keyframes slidedown {
  0% {
    opacity: 0;
    transform: translateY(-50px);
  }
  100% {
    opacity: 1;
    transform: translateY(0px);
  }
}
@keyframes slideup {
  0% {
    opacity: 1;
    transform: translateY(0px);
  }
  100% {
    opacity: 0;
    transform: translateY(-50px);
  }
}
</style>
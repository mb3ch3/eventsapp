<template>
    <div class="event-card">
      <img class="cardss" :src="event.featuredImage" alt="">
      <div class="det1">{{ event.name }}</div>
      <div class="det2">{{ event.location }}</div>
      <div class="det3">{{ event.date }}</div>
    </div>
  </template>

<script>
  export default {
    props: ['event'],
  };
</script>
  <style lang="scss" scoped>
    .event-card{
      // padding: 1px;
      // background: yellow;
      width: 400px;
      height: auto;
    }
    .cardss {
      // background-image: url('https://teamorange.in/wp-content/uploads/2017/01/event-management-blog-1-performance.jpg');
    // background-image: url('https://cdn.pixabay.com/photo/2017/12/08/11/53/event-party-3005668__340.jpg');
      // background-image: url('https://placekitten.com/400/400');
      // background-position: center;
      // background-size: cover;
      min-height: 100%;
      height: 250px;
      width: 100%;
      margin: 0;
      padding: 0;
    }
    .det1{
    font-family: 'Questrial', sans-serif;
    color: white;
    background: black;
    padding: 6px;
    width: 100%;
    text-transform: capitalize;
  }
  .det2{
    font-family: 'Questrial', sans-serif;
    color: black;
    background: white;
    border-bottom: lightsteelblue solid .5px;
    padding: 6px;
    width: fit-content;
    text-transform: capitalize;
  }
  .det3{
    font-family: 'Questrial', sans-serif;
    color: white;
    background: black;
    padding: 6px;
    width: fit-content;
    text-transform: capitalize;
    float: right;
  }
  </style>
<template>
    <div style="position:-webkit-sticky">
        <div class="header-nav">
            <div class="branding">
                <div class="logo">
                    <img src="../../assets/img/logo.png" alt="logo">
                </div>
                <div class="name">
                    <div class="main">
                        events app
                    </div>
                    <div class="motto">
                        find an event near you
                    </div>
                </div>
            </div>
            <div class="socials">
                <div class="social-item">
                    <i class="ri-facebook-fill"></i>
                </div>
                <div class="social-item">
                    <i class="ri-instagram-fill"></i>
                </div>
                <div class="social-item">
                    <i class="ri-linkedin-fill"></i>
                </div>
                <div class="social-item">
                    <i class="ri-twitter-fill"></i>
                </div>
                <div class="social-item">
                    <i class="ri-youtube-fill"></i>
                </div>
            </div>
        </div>
        <div class="navbar-nav">
            <div class="nav-items">
                <router-link to="/" class="nav-item">Home</router-link>
                <router-link to="/about" class="nav-item">About</router-link>
                <div class="nav-item">Search Venues</div>
                <div class="nav-item">Connect with Organizers</div>
                <div class="nav-item">Register an Event</div>
                <div class="nav-item">Contact Us</div>
            </div>
            <div class="extra-nav">
                <div class="search">
                    <i class="ri-search-2-line"></i>
                </div>
                <div class="buy-ticket">Register an Event!</div>
            </div>
        </div>
    </div>
    <!-- <router-link to="/" class="navbar-item">Home</router-link>
          <router-link to="/about" class="navbar-item">About</router-link> -->
  </template>
  <script>
    /* eslint-disable */
    export default {
      name: 'Nav',
    };
  </script>
  <style lang="scss" scoped>
    .header-nav{
        background: white;
        display: grid;
        grid-template-columns: auto auto;
        grid-template-rows: auto;
        align-items: center;
        justify-content: space-between;
        width: 86vw;
        margin-inline: auto;
        padding: 10px 0;
    }
    .branding{
        display: grid;
        grid-template-columns: 1fr 3fr;
        align-items: center;
        justify-content: center;
    }
    .logo{
        width: 3.5rem;
        height: auto;
        justify-self: center;
        padding: 0 2px;
    }
    .name{
        
        max-height: 7vh;
        display: grid;
        grid-template-columns: auto;
        grid-template-rows: 1fr auto;
        grid-gap: 0;
        padding: 0 5px 0px 3px;
        align-items: center;
    }
    .main{
        font-family: 'DM Serif Display', serif;
        text-transform: capitalize;
        font-size: 1.5rem;
    }
    .motto{
        font-family: 'Questrial', sans-serif;
        text-transform: capitalize;
        font-size: .6rem;
        padding: 0 3px;
    }
    .socials{
        display: grid;
        grid-template-columns: repeat(5,1fr);
        height: 100%;
        align-items:center;
        justify-content: flex-end;
    }
    .social-item{
        margin-left: 25px;
        font-weight: bolder;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .navbar-nav{
        border-top: solid 0.25px #b0c4de50;
        background: #b0c4de20;
        padding: 0 6.47vw;
        height: 100%;
        display: grid;
        grid-template-columns: auto auto;
        grid-template-rows: 1fr;
        align-items: center;
        justify-content: space-between;
    }
    .nav-items{
        display: grid;
        grid-template-columns: repeat(6,auto);
        justify-content: space-around;
    }
    .nav-item{
        font-family: 'Questrial', sans-serif;

        padding: 17px 25px;
        background: transparent;
        height: 100%;
        color: black;
    }
    .nav-item:hover{
        background: linear-gradient(to right,#2A2A72,#009FFD);
        transition: all .5s;
        color: white;
    }
    .extra-nav{
        display: grid;
        grid-template-columns: .5fr 2fr;
        align-items: center;
    }
    .search{
        margin: 0 20px;
        font-weight: bolder;
    }
    .buy-ticket{
        font-family: 'DM Serif Display', serif;
        background: linear-gradient(to right,#2A2A72,#009FFD);
        height: 100%;
        padding: 7px 12px;
        text-transform: capitalize;
        color: white;
        font-size: smaller;
    }
  </style>
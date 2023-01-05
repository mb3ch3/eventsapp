<template>
  <div class="registration">
    <div class="form">
        where and when ...!?
    </div>
    <div class="left-reg">
      <div class="topic">Toa form !!</div>
      <div class="other-topic">Register your event with us</div>
    </div>
    <div class="right-reg">
        <input type="text" v-model="email" placeholder="Kindly provide your email address">
        <i class="ri-chat-forward-line"></i>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>

.registration{
    background: #4682b440;
    display:grid;
    grid-template-columns: 3fr 1.5fr 2fr;
    grid-template-rows: auto;
    align-items: center;
    justify-content: space-between;
}
.topic{
    font-weight: bold;
    font-family: "Questrial", sans-serif;
    text-transform: capitalize;
    font-size: 27px;
}
.other-topic{
    font-weight: bold;
  font-family: "DM Serif Display", sans-serif;
  text-transform: capitalize;
}
.left-reg{
    padding: 20px 20px 10px 20px;
    display: grid;
    grid-template-columns: auto;
    grid-template-rows: 2rem 1.5rem;
    align-items: center;
    background: #4682b470;
    justify-content: flex-start;
    height: 100%;
}
.right-reg{
    padding: 10px 50px 10px 0;
    font-size: xx-large;
    text-align: right;
    background: #4682b470;
    height: 100%;
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-template-rows: auto;
    align-items: center;
    justify-content: center;
}
.right-reg input{
    padding: 10px 15px;
    width: 23rem;
    border:none;
    background: transparent;
    border-bottom: #2C3E50 2px solid;
}
.right-reg input:focus{
    border:none;
    outline: none;
    background: #D1E0EC;
    border-bottom: #2C3E50 2px solid;

}
.right-reg input::placeholder{
    font-family: "Questrial", sans-serif;
    color: #00000070;
    font-size: 20px;
    padding-left: 0;
    margin-left: 0;
}

.form{
    font-family: 'Bungee Shade', cursive;
    font-size: 40px;
    padding-left: 50px;
}
</style>
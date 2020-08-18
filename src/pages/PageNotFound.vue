<template>
  <div class="col-full" :class="$style.centered">
    <!--  make sure the class is unique  -->
    <h1 :class="$style.headingLarge">Page Not Found</h1>
    <p :class="$style.textLarge">
      Oops, this is not the page you are looking for. <br/>
      Click
      <router-link :to="{name: 'Home'}">here to go home</router-link>
      .
    </p>
  </div>
</template>

<script>
  export default {
    name: 'PageNotFound'
  }
</script>

<style module>
  .headingLarge {
    font-size: 100px;
  }
  .textLarge {
    font-size: 50px;
    font-weight: 100;
  }
  .centered {
    text-align: center;
  }
</style>

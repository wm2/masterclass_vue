<template>
  <div class="col-full" :class="$style.centered">
    <h1 :class="$style['heading-large']">Not Found
      <p :class="$style['text-large']">Oops, we couldn't find what you are looking for. Why don't you
        <router-link
        :to="{name: 'Home'}">
          go home instead?
        </router-link>
      </p>
    </h1>
  </div>
</template>

<script>
export default {

}
</script>

<style module>
  .heading-large {
    font-size: 100px;
  }
  .text-large {
    font-size: 50px;
    font-weight: 100;
  }
  .centered {
    text-align: center;
  }
</style>

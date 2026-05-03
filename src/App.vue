<script setup>
import { ref } from "vue";
let message = ref("This is the value for the text input yuppppp!!");

// bind this var into the template
// need to allow vue to track changes the this varibnale

let imageSrc = ref("/public/img/banner_1.jpg");

// getting the click event
function changeImage() {
  imageSrc.value = "/public/img/banner_2.jpg";
}

let className = ref("active");

let isInactive = ref(true);
let isCenter = ref(false);
</script>

<!-- do not really care about having the images in the branch just what we need to know -->
<!-- html elements have attributes, we can dynamically change them -->
<!-- use v-bind to bind data from the script to html elemetns -->
<!-- :attribute is the short hand for v-bind:attribute -->
<template>
  <h1>{{ message }}</h1>
  <img v-bind:src="imageSrc" alt="" />
  <br />

  <button @click="changeImage">Change Image</button>

  <br />

  <input type="text" v-bind:value="message" />

  <br />

  <p :class="className">Harry Potter</p>

  <p :class="{ inactive: isInactive, center: isCenter }">Hermione Granger</p>

  <p :class="['active', { inactive: isInactive, center: isCenter }]">
    Ron Weasley
  </p>
</template>

<style scoped>
img {
  max-width: 300px;
}

.active {
  color: green;
}

.inactive {
  color: red;
  text-decoration: line-through;
}

.center {
  text-align: center;
}
</style>

<script setup>
let message = "you suck nigger!";
function double_num(num) {
  return num * 2;
}

let number = 15;

// object
let o = {
  name: "John",
  age: 30,
};

let raw_html = "<span style='color: red;'>This is raw HTML</span>";
</script>

<template>
  <div>{{ message }}</div>
  <h1>{{ double_num(5) }}</h1>

  <p>number * 2 is = {{ double_num(5) }}</p>
  <hr />

  <h1>
    {{
      number > 10
        ? "The number is greater than 10!"
        : "The number is less than 10!"
    }}
  </h1>

  <hr />
  <h1>Print Object</h1>
  <p>Name: {{ o.name }}</p>
  <p>Age: {{ o.age }}</p>

  <!-- vue directives v-text and v-html -->
  <!-- v-text does this as just text does not render html at all -->
  <h1 v-text="message"></h1>
  <hr />

  <h1 v-html="raw_html"></h1>
</template>

<style scoped></style>

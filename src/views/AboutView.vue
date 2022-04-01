<template>
  <div class="about">
    <h1>Detalji knjiga</h1>
    <button onclick="history.back()">Go Back</button>
    {{url}}
    <router-view/>
  </div>
</template>

<script>

export default {
  props: ["url"],
  name: "AboutPage",
};

</script>




<style></style>

<template>
  <div class="home">
    <app-heading :scale="1">大見出し</app-heading>
    <app-heading :scale="2">中見出し</app-heading>
    <app-heading :scale="3">小見出し</app-heading>
  </div>
</template>
<script>
import AppHeading from "@/components/AppHeading";
export default {
  name: "Home",
  components: {
    AppHeading,
  },
};
</script>
<style>
.heading1 {
  color: #dc001a;
}
.heading2 {
  color: blue;
}
.heading3 {
  color: green;
}
</style>

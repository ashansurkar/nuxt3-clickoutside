<template>
  <div>
    <div class="parent" v-click-outside="clickedParent">
      Parent
      <div class="child" v-click-outside="clickedChild">Child</div>
    </div>
    <div>Clicked outside element: {{ clickedOutsideElement }}</div>
  </div>
</template>
<script setup>
const clickedOutsideElement = ref("");
const clickedChild = () => {
  clickedOutsideElement.value = "child";
};
const clickedParent = async () => {
  await new Promise((resolve, reject) => setTimeout(resolve, 1));
  clickedOutsideElement.value = "parent";
};
</script>
<style>
body {
  font-size: 2rem;
}
.parent {
  padding: 3rem;
  background: #888;
}
.child {
  padding: 3rem;
  margin: 2rem;
  background: white;
}
</style>

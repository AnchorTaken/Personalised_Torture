<template>
  <!-- 01. Follow the numbers and do the things in order of the numbers -->
  <!-- 01.1 This is the first thing you need to learn. HTMLTutorial is a component meaning its a tiny slice of code that has been brought up externally into this document but it displays exactly the same way as the normal code. -->
  <div class="hidden">
    <!-- I wrapped the component in a div with a class of hidden just so it doesnt show up in the dom -->
    <HTMLTutorial/>
    <JSTutorial/>
  </div>


  <!--  Challenges -->
  <div class="h-screen w-full flex">
  <ChallengeOne/>
  </div>
</template>

<script setup>
// 01.2 The components are brought in here
import HTMLTutorial from "./components/HTMLTutorial.vue";
import JSTutorial from "./components/JSTutorial.vue";
import ChallengeOne from "./components/challenges/ChallengeOne.vue"; // 01.3 Navigate to the Components folder and open HTMLTutorial.vue
</script>

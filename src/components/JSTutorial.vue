<template>
  <div class=""></div>
  <!-- 03.3 Below you will find a couple of divs. Those divs will have a v-if tag. What this tag does is checks for the value of the ref you gave it and displays the element if the condition is true -->
  <!-- 03.4 Because this element is checking for isRed and isRed is false it will not display -->
  <div class="text-red-500" v-if="isRed">This text is red</div>

  <!-- 03.5 This element on the other hand is checking for whether the isRed is false signified by "!" before isRed and thus this element will be displayed -->
  <div class="text-red-500" v-if="!isRed">This text is red</div>

  <!-- 03.6 There are a couple of ways you can check for logic in JavaScript -->
  <!-- Basic true or false statements  -->
  <div class="text-red-500" v-if="isRed === true">This text is red</div>
  <div class="text-red-500" v-if="isRed === false">This text is red</div>

  <!-- You can also check for the opposite of true or false -->
  <div class="text-red-500" v-if="isRed !== true">This text is red</div>
  <div class="text-red-500" v-if="isRed !== false">This text is red</div>

  <!-- 03.7 You can also stack checks. Below in the JS code i've created a isGreen state. Its the same exact state as the red but instead of false it is set to true by default-->
  <!--  03.8 Now lets check for whether the red and the green are both false-->
  <!-- 03.9 This piece of code will check whether both isRed and isGreen are both false and then display the elemnt otherwise it will be invisible  v-if="!isRed && !isGreen"  -->
  <div class="text-red-500" v-if="!isRed && !isGreen">This text is red</div>

  <!--  03.10 Alternatively you can check for one of the two values being true and show the element like below -->
  <div class="text-red-500" v-if="isRed || isGreen">This text is red</div>

  <!--  03.11 This can be mixed and matched to your desire. These will get significantly more complex later on but that will be your choice-->
  <!-- 03.12 Now that we have learned this. Lets go and build something with it. Go to challenges/challengeone.vue-->
</template>

<script setup>
//Imports
import {ref} from 'vue'; // 03.3 This is the import for the ref. This is needed for the state

// 03 Now to the fun part. This is the bread and butter of this software.
// First things first. You see how the tag at the top says <script setup> ? This is a specific subset of the scrip that and that changes how you write it a little bit.
// If you are ever looking for a slice of code for VUE which is the framework we are using and see something like this:

// export default {
//   data () {
//     return {
//       todos: {}
//     }
//   },
//   created () {
//     this.$http.get('/api/todos')
//         .then((response) => {
//           this.todos= response.data
//         })
//   },
//   methods: {
//     completeTodo (todo) {
//       todo.done = !todo.done
//     }
//   }
// }

// This code is not exactly correct and you can probably ignore it. You can ask ChatGPT to convert ^ into the code we use by telling gpt to convert it to  <script setup>

// It should look something like this

// import { ref, onMounted } from 'vue';
// import { useFetch } from '@/composables/useFetch'; // Let's assume you have a useFetch composable
//
// const todos = ref({});
//
// onMounted(async () => {
//   const { data } = await useFetch('/api/todos');
//   todos.value = data;
// });
//
// const completeTodo = (todo) => {
//   todo.done = !todo.done;
// };

// 03.1 Now that we have that out of the way. Let's get to the actual code.

// 03.2 This is called a state. Meaning that it stores a value that you can then check and change the website how you desire based on the outcome
// This needs a ref as an import and that was imported at the top. Imports always go at the top
// Now what we have a value is red we can check for it in the dom (dom refers to a fancy way of calling the user interface).
// When creating a state most times you want to give it a default value inside the (). that can be a boolean aka "true" or "false", number 23, string "hello world" and a bunch of other things

const isRed = ref(false);
// 03.8 I've created another ref below. This one is called isGreen and it is set to true. Go back up and see how I used this to preform more complex checks on states
const isGreen = ref(true);
</script>
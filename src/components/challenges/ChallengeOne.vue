<template>
  <!--04 Heres is our first component -->
  <!-- 04.1 In this component we have a bunch of nested elements (nested meaning inside one another) -->
  <!-- All I have done is just centered the container (parent that is holding everything tends to be called a container or a wrapper)-->
  <div class="m-auto w-4/12 space-y-6">
    <div class="flex">

      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Amet consequuntur dicta eligendi in
        nulla omnis quibusdam quos reiciendis sit voluptatem.</p>
    </div>
    <button class="mt-2 rounded-full bg-zinc-700 px-5 py-1 text-white">Change Color</button>
    <!--    04.4 Lets add some functionality to the button and call the function we just created  -->
    <!--    04.5 What I have done here is add an @onclick event that calls the function when it is triggered. An event is an interaction from the user in one way or another   -->
    <button class="mt-2 rounded-full bg-zinc-700 px-5 py-1 text-white" @click="toggleRed">toggleRed using a function
    </button>

    <!--    04.6 Alternatively you can change the state within the @click event itself shown in example below-->
    <button class="mt-2 rounded-full bg-zinc-700 px-5 py-1 text-white" @click="isRed.value = !isRed.value"> Toggled red
      within the @click event
    </button>
    <!--   ! Most of the times you can get away with changing state within the @click event but there are some edgecases where you need to call multiple functions within the same event and that can very quickly become tricky -->

    <!--    04.7 Now that we have added the buttons to toggle a state lets do something with it -->
    <!--    I grabbed the p tag from above. But I only want to display it when the isRed is equals to true because the text of this paragraph is red-->
    <!--    That can be done very easily using the v-if bind -->
    <p class="text-red-600" v-if="isRed">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Amet consequuntur dicta eligendi in
      nulla omnis quibusdam quos reiciendis sit voluptatem.</p>
    <!--    Now if you click on any of the buttons above the paragraph will appear and disappear accordingly -->

    <!--    04.8 Now for the challenge. I have a paragraph below. it is green and i want it to show up only when isGreen is true and isRed is false-->
    <p class="text-green-600">Lorem ipsum dolor sit amet, consectetur adipisicing elit. At iusto, maxime sint suscipit
      tempore voluptatum! Aliquam, facilis perspiciatis? Esse, praesentium.</p>
    <button class="mt-2 rounded-full bg-green-700 px-5 py-1 text-white"> Show Green</button>
    <!--04.9 Achieve that and the task is complete -->
  </div>
</template>
<script setup>
// Import our ref so that we have states that we can change live
import {ref} from "vue";

// Created a state called isRed and set it to false
const isRed = ref(false);

// 04.2 There are a couple of ways you can change the state
// One example being a change function like the one below
const toggleRed = () => {
  isRed.value = !isRed.value; // 04.3 What this function does is toggles (flips between) the value of isRed if the function is called. Lets call the function
}
</script>

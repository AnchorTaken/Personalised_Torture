<template>
  <!-- 05 Now lets make this a little more spicy  -->

  <div class="m-auto w-4/12 space-y-6">
    <!--    05.2 Lets begin by mapping all of our data. For this we will need another vue bind called v-for which goes through all of our data and mapps all of it out to individual objects -->
    <!--    05.3 Now then lets take our data and tell the v-for what todo-->
    <!--    item is our individual object we are going to be calling within the loop. Followed by i which is our index meaning the number of the object within the array (an array is just a list of values that can be mapped signified by []) -->
    <!--    after we declared what data we want to map it is a good idea to give it a :key to make sure there are no weird issues. we dont need to think too hard and just add the index to the key every time we add a key-->

    <div v-for="(item, i) in data" :key="i">
      <!-- 05.4 Now that we have mapped our data to this div we have access to it within this div.-->
      <!--      Now lets do something with this data -->
      {{ item.name }}
      <!--  Accessing data from the json is as easy as that. Take the "item" or whatever you called the singular item you want to map and then use the key (this time key means the name of the field you are trying to access within the array) to access that data -->

      <!--    05.5 Now I want you to map the rest of the data -->
      <div class=""></div>  <!--  Map the age over here -->

      <!--      05.6 Now its getting interesting. Nested arrays can be a BITCH at times but fear not. Youll get used to it -->
      <!--      Lets quicky map the favourite foods array -->

      <div class="mt-3">
        <h4 class="font-bold">Favourite Foods</h4>
        <div class="flex">
          <div class="mr-2" v-for="fFoods in item.favoriteFoods" :key="i">
            <!--   Notice how i put fFoods into the name im gonna use to map and not item and the key is also the index.
            Also notice how I am accessing item and then accessing favoriteFoods inside the item. so im mapping the children of the array inside the main data -->
            {{ fFoods }},
          </div>
        </div>

        <!--        05.7 Now for the challenge. I want you to take the data below and map out magicalAbilities like the rest of the data -->
      </div>
    </div>
  </div>
</template>
<script setup>
// 05.1 The data below is json. This data can be stored in a bagilion ways but it will be more or less the same layout all the time
// This data format is called JSON and is standard across the industry for how data is being passed to the front end. Which is what we are working with
// Lets use this data to display something interesting.
// For that we can do many many things. We can grab an individual pieces of data such as "name",  "age" or we can map (go through) the whole data set to display all of the data
// Lets do that

const data =
    [
      {
        "name": "Sailor Moon",
        "age": 14,
        "favoriteFoods": ["ice cream", "cake"],
        "magicalAbilities": {
          "primary": "Moon Tiara Action",
          "secondary": "Moon Healing Escalation"
        }
      },
      {
        "name": "Naruto Uzumaki",
        "age": 17,
        "favoriteFoods": ["ramen", "rice balls"],
        "magicalAbilities": {
          "primary": "Rasengan",
          "secondary": "Shadow Clone Jutsu"
        }
      },
      {
        "name": "Goku",
        "age": 35,
        "favoriteFoods": ["rice", "meat"],
        "magicalAbilities": {
          "primary": "Kamehameha",
          "secondary": "Instant Transmission"
        }
      }
    ]
</script>

<template>
  <div class="home">
    <br />
    <br />
    <br />
   
     <ul>
      <li v-for="item in commits" v-bind:key="item.url">
        Knjige <router-link :to ="'/commit/'+item.url"> {{item.url}} </router-link>
       </li>
    </ul>

  </div>
</template>

<script>

import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
 data: function() {
   return {
     commits: [],
   };
 },



 async mounted(){



//  fetch('http://cantab.elaclo.com:8000/books.json')
//  .then((response) => response.json())
//  .then((json) => console.log(json));
//   },
// }


let rezultat = await fetch("https://www.anapioficeandfire.com/api/books");
  let podaci  = await rezultat.json();
for (let item of podaci) {
  console.log(item.url);
    }
    
    this.commits = podaci;
  },
};





</script>
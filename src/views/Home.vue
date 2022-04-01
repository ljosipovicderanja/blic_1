<template>
  <div class="home">
    <ul>
      <li v-for="item in knjiga" v-bind:key="item.sha">
        Knjiga <router-link :to="'/knjiga/' + item.sha">{{item.url + " , " + item.name + ", " + item.authors }}</router-link>
      </li>
    </ul>
    
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',

  data() {
    return {
        knjiga: [],
    }
  },
 async mounted() {
    
    
    let rezultat = await fetch("https://www.anapioficeandfire.com/api/books");
     
     let podaci = await rezultat.json()
    
    for (let item of podaci) {
     console.log(item.sha);
    }
  this.knjiga = podaci;
  },
  
}
</script>

<template>
  <div class="home">
    <ol>
      <li v-for="knjiga in knjiga" :key="knjiga.url">
      <!--    <router-link :to="'/knjiga/' + knjiga.sha">{{knjiga.url + " , " + knjiga.name + ", " + knjiga.authors }}</router-link> -->
    <router-link :to="{name:'Knjiga', params: { isbn: knjiga.isbn, url: knjiga.url}}">{{ knjiga.name }} > {{knjiga.authors}}</router-link> 
      </li>
    </ol>
    
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name:'Home',
  data() {
    return {
      knjiga: []
    }
  },

 async mounted() {
     let rezultat = await fetch("https://www.anapioficeandfire.com/api/books")
     console.log("rezultat")
     let podatci = await rezultat.json() 
     this.knjiga = podatci 
 }

}
</script>

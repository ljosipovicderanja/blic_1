<template>
  <div>
    <ul>
      <li>Ime autora: {{knjiga.authors}}</li>
      <li>ISBN: {{knjiga.isbn}}</li>
      <li>Broj Stranica: {{knjiga.numberOfPages}}</li>
      <li>Zemlja podrjetla: {{knjiga.country}}</li>
      <li>Izdano: {{knjiga. released}}</li>
      <li>Likovi: {{likovi.length}}</li>
    </ul> 
     <button onclick="location.href='/'">
        Vrati na listu
      </button>

  </div>
</template>

<script>
export default {
  name: 'Knjiga',
  props: {
    isbn: String,
    url: String
  },

  data(){
    return{
      knjiga:[],
      likovi:0
    }
  },
  
  async created() {
    let rezultat = await fetch(this.url)
    let podatci = await rezultat.json() 
    this.knjiga = podatci
    this.likovi = podatci.characters
  }

}
</script>

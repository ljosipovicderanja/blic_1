<template>
  <div class="about">
    <h1>This is an about page</h1>
{{sha}}
{{url}}
    {{ $route.params.sha}}
    <router-view />
  </div>
</template>

<script>
export default {
props:[sha],
  data(){
    return {
      
    url:"https://www.anapioficeandfire.com/api/books/1",
    name:"A Game of Thrones",
    isbn:"978-0553103540",
    authors: ["George R. R. Martin"],
    numberOfPages:694,
    publisher:"Bantam Books",
    country:"United States",
    mediaType:"Hardcover",
    released:"1996-08-01T00:00:00",
    };
  },
  mounted () {

  },
    name: "Knjiga",

};
</script>


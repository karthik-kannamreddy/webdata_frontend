<template>
  <div class="container">
    <HeaderTop bookName="Workout Plan" authorName="Beginner" />

    <BookBox :books="books" />

</div>
</template>

<script>

import HeaderTop from './components/HeaderTop.vue'
import BookBox from './components/BookBox.vue'

// import axios from "axios";
export default {
  name: 'App',
  components: {    
    HeaderTop,
    BookBox
  },

  data(){
    return {
      books: []
    }

  },

  methods: {

    // promises

    async fetchBooks(){
      const res = await fetch('https://karthikfinalproject.herokuapp.com/api')
      const data = await res.json()
      console.log( data )
      return data
    }


  },
  async created(){
    this.books = await this.fetchBooks()
  }
}
  // mounted() {
  //   axios
  //       .get("https://karthikfinalproject.herokuapp.com/api")
  //       .then((res) => {
  //         console.log(res);
  //         this.books = res.data;
  //       })
  //       .catch((err) => {
  //         console.log(err);
  //       });
  // },

  // methods: {
  //
  //   // promises
  //
  //     async fetchBooks(){
  //       const url='https://karthikfinalproject.herokuapp.com/api';
  //       return new Promise((resolve, request)=>{
  //         try {
  //
  //           fetch(url).then((res)=> {return res.json()}).then((res)=>{
  //             resolve(
  //                 res.map(pos=>({
  //                   ...pos
  //                 }))
  //             )
  //           });
  //         }catch (err){
  //           request(err);
  //         }
  //       })
  //     }
  //
  //
  // },
  // async created(){
  //   this.books = await this.fetchBooks()
  //   console.log(this.books);
  // }


</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;
}

</style>

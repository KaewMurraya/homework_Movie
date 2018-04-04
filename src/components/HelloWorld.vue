<template>
  <div class="contrainer">
    <div class="columns">
      <div class="column is-4 offset-1">
        <label class="title is-2">Title : {{movieSelected}}</label>
      </div>
    </div>
    <div class="columns is-centered box">
      <div class="column is-2">
        <a @click="select('civilwar')">
          <img src="../assets/civilwar.jpg" alt="">
        </a>
        <br>
        <label class="title is-2">civilwar</label>
      </div>
      <div class="column is-2">
        <a @click="select('harry')">
          <img src="../assets/harry.jpg" alt="">
        </a>
        <br>
        <label class="title is-2">harry</label>
      </div>
      <div class="column is-2">
        <a @click="select('johnwick')">
          <img src="../assets/johnwick.jpg" alt="">
        </a>
        <br>
        <label class="title is-2">johnwick</label>
      </div>
      <div class="column is-2">
        <a @click="select('matrix')">
          <img src="../assets/matrix.jpg" alt="">
        </a>
        <br>
        <label class="title is-2">matrix</label>
      </div>
      <div class="column is-2">
        <a @click="select('thor')">
          <img src="../assets/thor.jpg" alt="">
        </a>
        <br>
        <label class="title is-2">thor</label>
      </div>
    </div>
      <div class="columns is-centered">
        <div v-for="(d,index) in data.civilwar" :key="index">
          <div v-if="!d.seated">
              <button class="button is-medium is-success is-outlined"> {{d.id}}({{d.price}}) </button>
            </div>
            <div v-else>
              <button class="button is-medium is-danger" disabled> {{d.id}}({{d.price}}) </button>
            </div>
      </div>
    </div>
  </div>
</template>

<script>
import data from '../Others/movie.json'
export default {
  name: 'HelloWorld',
  data () {
    return {
      data,
      movieSelected: ''
    }
  },
  methods: {
    select (title) {
      this.movieSelected = title
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

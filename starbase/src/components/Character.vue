<template>
  <div class="char" @click="switchCharacter">
  <h3>{{character.name}}</h3>
  <p>Hair: {{character.hair_color}}</p>
  <p>Gender: {{character.gender}}</p>
  </div>
</template>

<script type="text/javascript">
  export default {
    props: ['id'],
    data() {
      return {
        character: {},
      }
    },
    methods: {
      fetchCharacter(id){
        fetch(`http://swapi.co/api/people/${id}`, {
          method: 'GET',
        })
        .then(response => response.json())
        .then(json => this.character = json)
      },
      switchCharacter(){
        let rand = Math.floor(Math.random() * 83) + 1
        this.fetchCharacter(rand)
      },
    },
    created() {
      this.fetchCharacter(this.id)
    },
  }
</script>

<style type="text/css">
  .char{
    cursor: pointer;
    float: left;
    display: block;
    background-color: #fff;
    width: 250px;
    color: #444;
    margin: 10px;
    border-radius: 10px;
  }
  .char:hover{
    background-color: #fffed8;
  }
</style>

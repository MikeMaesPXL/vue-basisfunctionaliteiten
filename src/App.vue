<script>
export default {
  data: function() {
    return {
      title: 'Dit is een titel',
      intro: 'Dit is een intro',
      name: 'Mike Maes',
      age: '21',
      webpage: 'https://vuejs.org/',
      showMe: false,
      racoon: 'RACOON.jpg',
      duck: 'DUCK.png',
      buttonText: 'Change Picture'
    }
  },

  methods : {
    textEvent() {
      return "aaaaa"
    },
    dynamicValue() {
      let randomNumber = Math.random(0, 1)
      return randomNumber < 0.5 ? 'Wij verkopen de beste producten...' : 'Wie zoekt die vindt!';
    },
    ageUp(getalYeet) {
      let age = 21
      return age + getalYeet;
    },
    randomNumber() {
      let randomNumber = Math.random(0, 1)
      return randomNumber;
    },
    changePicture(racoon, buttonName) {
      this.duck = racoon;
      this.buttonText = `${buttonName}`
    }
  }
}
</script>

<template>
  <h1>Welkom in de Vue App</h1>
  <h2>{{ title }}</h2>
  <p>{{ intro }}</p>
  <img v-if="duck" v-on:click="showMe = true" :src="'/assets/' + duck" alt="duck">
  <button v-if="showMe" v-on:click="showMe = false" >Verberg mij</button>
  <button v-on:click="changePicture(racoon, 'Text Gewijzigd')">{{ buttonText }}</button>
  <h3>{{ textEvent().toUpperCase() }}</h3>
  <p>{{ dynamicValue() }}</p>

  <h2>{{ name }}</h2>
  <p>{{ age }}</p>
  <p>{{ ageUp(5) }}</p>
  <p>{{ randomNumber() }}</p>
  <a :href="webpage">Press this link</a>
  <input @click="ageUp(1)" type="text" :value="name">

</template>

<style>
  img {
    width: 75%;
  }
  input {
    margin-left: 10px;
    padding: 5px;
  }
</style>

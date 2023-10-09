<script>
export default {
  data: function() {
    return {
      title: 'Dit is een titel',
      intro: 'Dit is een intro',
      duck: 'DUCK.png',
      name: 'Mike Maes',
      age: '21',
      webpage: 'https://vuejs.org/'
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
    ageUp() {
      let age = 21
      return age + 5
    },
    randomNumber() {
      let randomNumber = Math.random(0, 1)
      return randomNumber
    }
  }
}
</script>

<template>
  <h1>Welkom in de Vue App</h1>
  <h2>{{ title }}</h2>
  <p>{{ intro }}</p>
  <img :src="'/assets/' + duck" alt="duck">
  <h3>{{ textEvent().toUpperCase() }}</h3>
  <p>{{ dynamicValue() }}</p>

  <h2>{{ name }}</h2>
  <p>{{ age }}</p>
  <p>{{ ageUp() }}</p>
  <p>{{ randomNumber() }}</p>
  <a :href="webpage">Press this link</a>
  <input type="text" :value="name">
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

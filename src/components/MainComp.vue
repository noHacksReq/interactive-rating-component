<script>
export default {
  data() {
    return {
      cardFrontSide: true
    }
  },
  methods: {
    flipCard() {
        this.cardFrontSide = !this.cardFrontSide;
    }
  }
}
</script>

<template>
  <div class="card front"
  v-if="cardFrontSide">
    <h1>How did we do?</h1>
    <p>Please let us know how we did with your support request. All feedback is appreciated to help us improve our offerings!</p>
    <ul>
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
    </ul>
    <button @click="flipCard">Submit</button>
  </div>
  <div class="card back"
  v-else>
    <h1>back of card</h1>
    <button @click="flipCard">Submit</button>
  </div>

</template>

<style>
  ul {
    list-style: none;
    display: flex;
  }

  .card {
    height: 250px;
    width: 250px;
    background-color: black; 
    border-radius: 25px;
    display: flex;
    flex-direction: column;
  }

  .mainCardFront {
    
    color: white;
    
  }
</style>
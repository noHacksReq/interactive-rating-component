<script>
export default {
  data() {
    return {
      cardFrontSide: true,
      ratings: [
        {star: 1,
        id: 1,
        value: 1},
        {star: 2,
        id: 2,
        value: 2},
        {star: 3,
        id: 3,
        value: 3},
        {star: 4,
        id: 4,
        value: 4},
        {star: 5,
        id: 5,
        value: 5}
      ]
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
  <div class="starBg">
  <svg width="17" height="16" xmlns="http://www.w3.org/2000/svg"><path d="m9.067.43 1.99 4.031c.112.228.33.386.58.422l4.45.647a.772.772 0 0 1 .427 1.316l-3.22 3.138a.773.773 0 0 0-.222.683l.76 4.431a.772.772 0 0 1-1.12.813l-3.98-2.092a.773.773 0 0 0-.718 0l-3.98 2.092a.772.772 0 0 1-1.119-.813l.76-4.431a.77.77 0 0 0-.222-.683L.233 6.846A.772.772 0 0 1 .661 5.53l4.449-.647a.772.772 0 0 0 .58-.422L7.68.43a.774.774 0 0 1 1.387 0Z" fill="#FC7614"/></svg>
</div>
    <h1 class="cardTitle">How did we do?</h1>
    <p class="cardFrCont">Please let us know how we did with your support request. All feedback is appreciated to help us improve our offerings!</p>
    <ul class="ratingLi">
      <li v-for="rating in ratings" :key="rating.id"
      class="rating">
      <div class="ratingStyle">
        {{ rating.star }}
      </div>
      </li>
    </ul>
    <button class="submitBtn"
     @click="flipCard">Submit</button>
  </div>
  <div class="card back"
  v-else>
    <h1 class="cardTitle">back of card</h1>
    
    <button @click="flipCard">Submit</button>
  </div>

</template>

<style>
* {
  outline: 1px solid white;
}
  .ratingLi {
    list-style: none;
    display: flex;
    width: 100%;
    padding: 0;
    margin: 0 auto;
  }

  .card {
    min-height: fit-content;
    max-height: 44%;
    width: 22vw;
    padding: 25px;
    background-color: hsl(213, 19%, 18%); 
    border-radius: 25px;
    display: flex;
    flex-direction: column;
    
  }

  .cardTitle {
    color: hsl(0, 0%, 100%);
    text-align: left;
    margin-bottom: 0;
  }

  .cardFrCont {
    text-align: left;
    color: hsl(217, 12%, 63%);
  }


  .starBg {
    display: flex;
    justify-content: center;
    width: 20px;
    background-color:  hsl(213, 19%, 18%);
    padding: 2%;
    border-radius: 50%;
    
  }

  .rating {
    color: white;
    height: 100%;
    width: 100%;
    
  }

  .ratingStyle {
    display: flex;
    justify-content: center;
    
    background-color: hsl(217, 12%, 63%);
    
    border-radius: 50%;
    padding:20px;
    
  }
  
  .submitBtn {
   background-color: hsl(25, 97%, 53%);
   border: none;
   height: 8vh;
   width: 99%;
   margin: auto;
   border-radius: 10px;
  }

  .submitBtn:hover {
    background-color: hsl(0, 0%, 100%);
  }




</style>
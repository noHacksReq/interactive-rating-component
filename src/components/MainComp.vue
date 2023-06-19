<script>

export default {
  data() {
    return {
      cardFrontSide: true,
      chosenVal: 0,
      ratings: [
        {star: 1,
        id: 1,
        value: 1,
        selected: false},
        {star: 2,
        id: 2,
        value: 2,
        selected: false},
        {star: 3,
        id: 3,
        value: 3,
        selected: false},
        {star: 4,
        id: 4,
        value: 4,
        selected: false},
        {star: 5,
        id: 5,
        value: 5,
        selected: false}
      ]
    }
  },
  methods: {
    flipCard() {
        this.cardFrontSide = !this.cardFrontSide;
    },
    activeRating(e) {
      
      e.selected = !e.selected;
            
      this.chosenVal = e.value
      this.ratings.map(function(i) {
       console.log(i.selected)
       if(i.value === e.value ) {
        
        i.selected = true
       }else{
        i.selected = false
       }
      })
      
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
    <p class="cardCont">Please let us know how we did with your support request. All feedback is appreciated to help us improve our offerings!</p>
    <ul class="ratingLi">
      <li class="ratingStyle"
      :class="[rating.selected ? 'activeRatingStyle' : 'rating']"
       v-for="rating in ratings" :key="rating.id"
      @click="activeRating(rating)">
      <div >
        {{ rating.star }}
      </div>
      </li>
    </ul>
    <button class="submitBtn"
     @click="flipCard">Submit</button>
  </div>
  <div class="card back"
  v-else>
    <div class="ratingDis">You selected {{ chosenVal }} out of 5</div>
    <h1 class="cardTitle">Thank You!</h1>
    <p class="cardCont">We appreciate you taking the time to give us a rating. If you ever need more support, don't hesitate to get in touch!</p>
    <button @click="flipCard">Submit</button>
  </div>

</template>

<style>


* {
 
}

.card {
  max-width: 22vw;
  min-height: 330px;
  font-size: 15px;
  padding: 25px 25px 12px 25px;
  background-color: var(--VeryDarkBlue); 
  border-radius: 25px;
  display: flex;
  flex-direction: column;
  font-weight: 400;
  }

  .back {
    align-items: center;
  }

  .ratingDis {
    color: hsl(25, 97%, 53%);
    background-color: hsl(216, 12%, 8%);
    padding: 8px;
    border-radius: 50px;

  }

  .cardTitle {
    color: hsl(0, 0%, 100%);
    text-align: left;
    margin-bottom: 0;
    font-weight: 700;
  }

  .cardCont {
    text-align: left;
    color: hsl(217, 12%, 63%);
    font-weight: 400;
  }


  .starBg {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    width: 20px;
    height: 20px;
    background-color: var(--DarkBlue);
    padding: 2%;
    border-radius: 50%;
    
  }

  .ratingLi {
    list-style: none;
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin-top: 45px;
    padding: 0;
    font-weight: 400;;
  }
  
  .rating {
    color: white;
    background-color: var(--DarkBlue);
  }

  .ratingStyle {
    display: flex;
    justify-content: center;
    flex-direction: column;
    height: 25px;
    width: 25px;
    
    color: var(--White);
    border-radius: 50%;
    padding:1vw;
    cursor: pointer;
  }

  .ratingStyle:hover {
    background-color:  var(--LightGrey);
  }

  .activeRatingStyle {
    background-color: var(--Orange);
    color:  var(--White);
  }
  
  .submitBtn {
   background-color: var(--Orange);
   border: none;
   height: 50px;
   width: 99%;
   margin: 010% 0 5%;
   border-radius: 50px;
  }

  .submitBtn:hover {
    background-color: hsl(0, 0%, 100%);
  }

</style>
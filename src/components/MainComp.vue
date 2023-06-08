<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<template>
  <div class="mainCardFront">
    <h1>How did we do?</h1>
    <p>Please let us know how we did with your support request. All feedback is appreciated to help us improve our offerings!</p>
    <ul>
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
    </ul>
    <button>Submit</button>
  </div>
</template>

<style>
  ul {
    list-style: none;
    display: flex;
  }

  .mainCardFront {
    height: 250px;
    width: 250px;
    color: white;
    background-color: black; 
    border-radius: 25px;
    display: flex;
    flex-direction: column;
  }
</style>
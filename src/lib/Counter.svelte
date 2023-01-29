<script lang="ts">
  let count: number = 0
  const increment = () => {
    count += 1
  }
  const reset = () => {
    count = 0
  }
  const timer = () => {
    if ( count == 1 ) {
      setTimeout() {
        
      }
    }
  }
</script>

<div class="card" >{ count }</div>
<button type="button" class="counter-button click-button" on:click={increment}>
  Click
</button>
<button type="button" class="counter-button reset-button" on:click={reset}>
  Reset
</button>

<style lang="scss">
  .card{
    width: 90vw;
    max-width: 500px;
    height: 200px;
    font-size: 10em;
    margin: 15px auto;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 8px solid #fff017c4;
  }
    .counter-button {
      width: 40%;
      max-width: 250px;
      min-width: 120px;
      height: 80px;
      font-family: Roboto, sans-serif;
      font-weight: bold;
      font-size: 35px;
      color: white;
      border: 2px solid white;
      border-radius: 15px;
      margin: 5px 15px;
      transition: 0.5s;
      cursor: pointer;
    }
    .counter-button:hover {
      background-color: #00471b;
    }
    .counter-button:active {
      background-color: #018634;
      box-shadow: 0px 10px 88px 15px rgba(1,134,52,0.75);
      -webkit-box-shadow: 0px 10px 88px 15px rgba(1,134,52,0.75);
      -moz-box-shadow: 0px 10px 88px 15px rgba(1,134,52,0.75);
    }
    .click-button {
      background-color: #ff3e00;
    }
    .reset-button {
      background-color: #bd34fe;
    }
</style>
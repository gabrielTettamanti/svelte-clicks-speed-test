<script lang="ts">
  import Board from "./Board.svelte";

  let count: any = 0
  let timeoutID
  let intervalID
  let timeLeft = 20
  let board: Array<String> = []
    
    const increment = () => {
      if ( typeof count == 'number') {
        count += 1
      }
      if ( count == 1 ) {
        timeoutID = setTimeout(() =>{
          count = count*3 + " Cs/m"
          board = [...board, count]
      }, 20000)
      intervalID = setInterval(function() {
        timeLeft--
        if (timeLeft == 0) {
          clearInterval(intervalID);
          timeLeft = 20
        }
      }, 1000);
    }
  }

  const reset = () => {
      count = 0
      clearTimeout(timeoutID)
      clearInterval(intervalID)
      timeLeft = 20
  }
</script>

<div class="card" >{ count }</div>
<button type="button" class="counter-button click-button" on:click={increment}>
  Click
</button>
{#if typeof count != 'number' || timeLeft == 20}
  <button type="button" class="counter-button reset-button" on:click={reset}>
    Reset
  </button>
{:else}
  <button type="button" class="counter-button reset-button timer-button" on:click={reset}>
    {timeLeft + 's'}
  </button>
{/if}
<Board board={ board }/>

<style lang="scss">
  .card{
    width: 90vw;
    max-width: 500px;
    min-height: 150px;
    font-size: 4.5em;
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
    .timer-button {
      transition: 1s;
      animation-name: shadow-second;
      animation-duration: 1s;
      animation-iteration-count: infinite;
      animation-timing-function: linear;
    }
    .timer-button:hover {
      background-color: gray;
      color: red;
      border: red 2px solid;
    }
    @keyframes shadow-second {
      0% {
        box-shadow: 0px -10px 25px 15px rgba(189,52,254,0.9);
        -webkit-box-shadow: 0px -10px 25px 15px rgba(189,52,254,0.9);
        -moz-box-shadow: 0px -10px 25px 15px rgba(189,52,254,0.9);
      }
      25% {
        box-shadow: 10px 0px 25px 15px rgba(189,52,254,0.9);
        -webkit-box-shadow: 10px 0px 25px 15px rgba(189,52,254,0.9);
        -moz-box-shadow: 10px 0px 25px 15px rgba(189,52,254,0.9);
      }
      50% {
        box-shadow: 0px 10px 25px 15px rgba(189,52,254,0.9);
        -webkit-box-shadow: 0px 10px 25px 15px rgba(189,52,254,0.9);
        -moz-box-shadow: 0px 10px 25px 15px rgba(189,52,254,0.9);
      }
      75% {
        box-shadow: -10px 0px 25px 15px rgba(189,52,254,0.9);
        -webkit-box-shadow: -10px 0px 25px 15px rgba(189,52,254,0.9);
        -moz-box-shadow: -10px 0px 25px 15px rgba(189,52,254,0.9);
      }
      100% {
        box-shadow: 0px -10px 25px 15px rgba(189,52,254,0.9);
        -webkit-box-shadow: 0px -10px 25px 15px rgba(189,52,254,0.9);
        -moz-box-shadow: 0px -10px 25px 15px rgba(189,52,254,0.9);
      }
    }
</style>
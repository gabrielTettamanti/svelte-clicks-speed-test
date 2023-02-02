<script lang="ts">
  export let board: Number[]

  const currentTime = () => {
    const date = new Date()
    const [hour, minutes, seconds] = [date.getHours(), date.getMinutes(), date.getSeconds()];
    return hour + ':' + minutes + ":" + seconds
  }
</script>

<div class="board-container">
  {#each board as item, i}
    {#if i < 5}
      <div class={`board-item ${'position-' + i}`}>
        <p class="board-mark">{ (item.valueOf() / 3) + 'Cs' }</p>
        <p class="board-mark">{ item + 'Cs/m' }</p>
        <p class="board-mark">{ currentTime() }</p>
      </div>
    {/if}
  {/each}
</div>

<style lang="scss">
  .board-container {
    border: 1px solid #fff0172c;
    width: 90vw;
    max-width: 500px;
    margin: 15px auto;
  }
    .board-item {
      margin: 5px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 30px;
      color: white;
    }
    .position-0 {
      background-color: gold;
      color: black;
      font-weight: 600;
    }
    .position-1 {
      background-color: silver;
      color: black;
      font-weight: 600;
    }
    .position-2 {
      background-color: #cd7f32;
      font-weight: 600;
    }
      .board-mark {
        font-size: 1.5em;
        margin: 0 20px;
        min-width: 100px;
      }
  @media (max-width: 480px) {
    .board-mark {
      font-size: 1.5em;
      margin: 0 2px;
      min-width: 0px;
    }
  }
</style>

<script lang="ts">
  export let board: Number[]
</script>

<div class="board-container">
  {#each board as item, i}
    <div class={`board-item ${'position-' + i}`}>
      <p class="board-mark">{ item + ' Cs/m' }</p>
    </div>
  {/each}
</div>

<style lang="scss">
  .board-container {
    border: 1px solid #fff017c4;
    width: 90vw;
    max-width: 500px;
    margin: 15px auto;
  }
    .board-item {
      margin: 5px auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 90%;
      height: 30px;
      color: white;
    }
    .position-0 {
      background-color: gold;
    }
    .position-1 {
      background-color: silver;
    }
    .position-2 {
      background-color: #cd7f32;
    }
      .board-mark {
        font-size: 1.5em;
        margin: auto;
      }
</style>

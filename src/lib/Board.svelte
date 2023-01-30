<script lang="ts">
  export let board: Number[]
  // export let orderedBoard: Number[] = board.sort(function(a, b){return a.valueOf() - b.valueOf()});
</script>

<div class="board-container">
  {#each board as item}
    <div class="board-item">
      <p class="board-mark">{ item }</p>
      <div class="board-item-icons">
        <div class="board-item-icon board-share-icon">
          <i class="fa-solid fa-share-nodes" />
        </div>
        <div class="board-item-icon board-xmark-icon">
          <i class="fa-solid fa-xmark" />
        </div>
      </div>
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
      .board-mark {
        font-size: 1.5em;
      }
      .board-item-icons {
        color: #242424;
        font-size: 1em;
        display: flex;
      }
        .board-item-icon {
          display: flex;
          justify-content: center;
          align-items: center;
          width: 70px;
          height: 28px;
          padding: 10px;
          margin: 15px;
          border-radius: 20px;
          background-color: white;
          transition: .5s;
        }
        .board-share-icon:hover {
          background-color: #25D366;
        }
        .board-xmark-icon:hover {
          background-color: red;
        }
</style>

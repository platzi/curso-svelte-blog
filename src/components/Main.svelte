<style>
  .Main-container {
    display: grid;
    grid-template-columns: minmax(auto, 1024px);
    justify-content: center;
    align-items: center;
  }
  .Main-content {
    margin: 2em 0 0 0;
    display: grid;
    justify-content: space-between;
    grid-gap: 60px;
    grid-template-columns: 3fr 1fr;
  }
</style>

<main>
  <div class="Main">
    <div class="Main-container">
      <div class="Main-content">
        <slot />
        <div class="Sidebar">Sidebar</div>
      </div>
    </div>
  </div>
</main>

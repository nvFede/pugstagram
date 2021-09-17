<style lang="scss">
  .main {
    display: grid;
    grid-template-columns: minmax(auto, 936px);
    justify-content: center;
    background-color: #fafafa;
    &__container {
      display: grid;
      grid-template-columns: 3fr 1fr;
      grid-gap: 2em;
      padding: 5em 0;
    }
  }
</style>

<main class="main">
    <div class="main__container">
       <slot /> 
    </div>
</main>



<style lang="scss">
  .share {
    border: 1px solid rgba(219, 219, 219, 1);
    border-radius: 4px;
    background-color: white;
    margin: 0 0 2em 0;
    width: 300px;
    height: 80px;
    position: absolute;
    top: 300px;
    left: 30%;
    z-index: 9;
    padding: 1em;
    &__head {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    &__head h2 {
      font-size: 16px;
    }
    &__head i {
      cursor: pointer;
    }
    &__content a {
      display: flex;
      align-items: center;
      text-decoration: none;
      color: black;
      font-size: 14px;
      margin: 2em 0 0 0;
    }
    &__content i {
      color: #3b5998;
      margin: 0 0.5em 0 0;
      font-size: 20px;
    }
  }
 
</style>

<div class="share">
    <div class="share__head">
        <h2>Share</h2>
        <i class="fas fa-time-circle" on:click/>

        <div class="share__content">
            <a href="https://www.facebook.com/sharer.php?&u=https://pugstagram.co">
                <i class="fab fa-facebook-square" />
                Share on Facebook
            </a>
        </div>

    </div>
</div>
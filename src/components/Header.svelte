<script>

	import { count } from '../store/store.js';
  import { get } from 'svelte/store';

</script>
<style lang="scss">

  .header {
    background-color: white;
    position: fixed;
    width: 100%;
    &__container {
      grid-template-columns: minmax(auto, 936px);
      display: grid;
      justify-content: center;
      background-color: white;
      border-bottom: 1px solid rgba(38, 38, 38, 0.4);
    }
    &__content {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0.5em;
    }
    ul {
      list-style: none;
    }
    li {
      display: inline-block;
      margin: 0 0 0 1em;
    }
    i {
      font-size: 16px;
      color: rgba(38, 38, 38, 0.7);
      cursor: pointer;
    }
    h1 {
      padding: 0;
      margin: 0;
      font-size: 28px;
      color: black;
      font-family: "Pacifico", cursive;
      cursor: pointer;
      position: relative;
      background: #fff;
      mix-blend-mode: multiply;
      display: inline-block;
      &:before {
        content: "";
        display: block;
        width: 100%;
        height: 100%;
        background: radial-gradient(circle at top left, #f09433, #bc1888);
        mix-blend-mode: screen;
        position: absolute;
        top: 0;
        left: 0;
      }
    }
  }    
   

</style>

<div class="header">
  <div class="header__container">
    <div class="header__content">
      <div class="header__logo">
        <h1>Pugstagram</h1>
      </div>
      <div class="header__nav">
        <ul>
          <li><i class="fas fa-heart" />
            {$count ? $count : ''}
          </li>
          <li><i class="fas fa-user-alt"></i></li>
        </ul>
      </div>
    </div>
  </div>
</div> 

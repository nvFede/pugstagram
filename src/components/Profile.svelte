<script>
    export let nickname;
    export let name;
</script>

<style lang="scss">

  .profile {
    &__content {
      display: flex;
      align-items: center;
    }
    &__avatar img {
      width: 42px;
      height: 42px;
      border-radius: 50%;
    }
    &__info {
      margin: 0 0 0 0.5em;
    }
    &__info h2 {
      font-size: 14px;
      color: black;
      margin: 0;
      padding: 0;
    }
    &__info span {
      font-size: 12px;
      font-weight: normal;
    }
  }

</style>

<div class="profile">
    <div class="profile__content">
        <div class="profile__avatar"><img src="" alt=""></div>
        <div class="profile__info">
            <h2>{nickname}</h2>
            <span>{name}</span>
        </div>
    </div>
</div>   

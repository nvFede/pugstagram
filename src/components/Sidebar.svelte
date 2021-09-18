<script>
    import Profile from './Profile.svelte';
    import Stories from './Stories.svelte';
    import Footer from './Footer.svelte';

    export let nickname;
    export let name;
</script>

<style lang="scss">
  .sidebar {
    position: relative;
    padding: 0.5em 0 0 0;
    &__container {
      position: fixed;
    }
  }
</style>

<aside class="sidebar">
    <div class="sidebar__container">
        <Profile {nickname} {name} />
        <Stories />
        <Footer />
    </div>
</aside>
<script>
	import { onMount } from 'svelte';
	
  
	import Header from './components/Header.svelte';
	import Main from './components/Main.svelte';
	import Sidebar from './components/Sidebar.svelte';
	import Timeline from './components/Timeline.svelte';

	const API = "https://us-central1-pugstagram-co.cloudfunctions.net/data";
	let data = {};

	onMount(async () => {
		const r = await fetch(API);
		data = await r.json();
		console.log(data);
	});

</script>
<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;400;700&family=Pacifico&display=swap');

 :global(body) {
    background-color: #fafafa;
    color: rgba(38, 38, 38, 0.7);
    font-family: "Lato", sans-serif;
    margin: 0;
    padding: 0;
  }
  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
  
</style>

<Header />
<Main>  
	<Timeline posts={data.posts} />
	<Sidebar {...data.user} />
</Main>
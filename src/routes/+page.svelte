<script>
	import Intro from '$lib/components/Home/Intro.svelte';
	import Works from '$lib/components/Home/Works.svelte';
	import Reviews from '$lib/components/Home/Reviews.svelte';
	import Contacts from '$lib/components/Home/Contacts.svelte';
</script>

<svelte:head>
	<title>Ремонтная артель</title>
	<meta name="description" content="Сообщество мастеров отделочников различной специализации, работа и цены без посредников" />
</svelte:head>

<Intro />
<Works />
<Reviews />
<Contacts />

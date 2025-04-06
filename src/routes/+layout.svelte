<script>
	const { children } = $props();
	import '$lib/scss/styles.scss';

	import { onMount } from 'svelte';
	import AOS from 'aos';
	import 'aos/dist/aos.css';

	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

	onMount(() => {
		AOS.init({
			offset: 120, // Отступ перед началом анимации (px)
			delay: 0, // Задержка перед началом анимации (ms)
			duration: 400, // Длительность анимации (ms)
			easing: 'linear', // Тип анимации (например, 'ease', 'linear', 'ease-in-out')
			once: false, // Если true – анимация сработает только 1 раз при скролле вниз
			mirror: false, // Если true – анимация будет работать при скролле вверх
			anchorPlacement: 'top-bottom' // Где должен находиться элемент, чтобы анимация сработала
			// disable: () => window.innerWidth < 768 // Отключение анимации (можно передать функцию или true/false)
		});
	});
</script>

<Header />
<main>
	{@render children()}
</main>
<Footer />

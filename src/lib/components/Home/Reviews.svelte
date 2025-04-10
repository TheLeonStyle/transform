<script>
	import KeenSlider from 'keen-slider';
	import { onMount } from 'svelte';

	let sliderRef = null;
	let sliderInstance = null;
	let currentSlide = 0;

	function bulletClick(index) {
		if (sliderInstance) {
			sliderInstance.moveToIdx(index);
		}
	}

	onMount(() => {
		sliderInstance = new KeenSlider(
			sliderRef,
			{
				loop: true,
				mode: 'free-snap',
				slides: {
					origin: 'center',
					perView: 1,
					spacing: 10
				}
			},
			[
				(slider) => {
					let timeout;
					let mouseOver = false;
					function clearNextTimeout() {
						clearTimeout(timeout);
					}
					function nextTimeout() {
						clearTimeout(timeout);
						if (mouseOver) return;
						timeout = setTimeout(() => {
							slider.next();
						}, 3000);
					}
					slider.on('created', () => {
						slider.container.addEventListener('mouseover', () => {
							mouseOver = true;
							clearNextTimeout();
						});
						slider.container.addEventListener('mouseout', () => {
							mouseOver = false;
							nextTimeout();
						});
						nextTimeout();
					});
					slider.on('dragStarted', clearNextTimeout);
					slider.on('animationEnded', nextTimeout);
					slider.on('updated', nextTimeout);

					// Обновляем индекс текущего слайда при его изменении
					slider.on('slideChanged', (s) => {
						currentSlide = s.track.details.rel;
					});
				}
			]
		);
	});
</script>

<section class="reviews">
	<div class="reviews__container">
		<h2 class="reviews__heading" data-aos="fade-right">Отзывы клиентов</h2>

		<ul bind:this={sliderRef} class="reviews__items" data-aos="zoom-in">
			<li class="reviews__item keen-slider__slide">
				<div class="reviews__image">
					<img src="/img/reviews/1.jpg" alt="" />
				</div>

				<div class="reviews__content">
					<p class="reviews__text">
						Я остался в полном восторге от выполненной реставрации исторического фасада нашего особняка. С самого начала работ команда специалистов
						продемонстрировала высокий уровень профессионализма и глубокое понимание особенностей архитектурного наследия. Каждый этап проекта был тщательно
						спланирован: от первоначального осмотра здания и выбора материалов до финишной отделки. Мастера использовали только натуральные материалы, что
						позволило сохранить подлинную структуру фасада и придать ему особую элегантность. Мне особенно понравилось, как специалисты восстановили
						декоративные элементы, такие как лепнина и резные детали, не нарушая оригинальный замысел архитектора. Благодаря их усилиям здание получило новую
						жизнь, сохранив свою историческую ценность и в то же время обретя современное звучание. Отдельно хочу отметить прозрачность сметы и своевременность
						выполнения работ. Все вопросы обсуждались и решались оперативно, что создавало ощущение полного контроля над процессом. В целом, сотрудничество с
						этой командой стало для меня приятным и уверенным шагом в сохранении культурного наследия.
					</p>
					<p class="reviews__name">Иван Петров</p>
					<p class="reviews__role">Владелец частного особняка</p>
				</div>
			</li>
			<li class="reviews__item keen-slider__slide">
				<div class="reviews__image">
					<img src="/img/reviews/2.webp" alt="" />
				</div>

				<div class="reviews__content">
					<p class="reviews__text">
						Процесс создания акцентной стены в интерьере моей квартиры превзошёл все ожидания. С самого первого этапа работы специалисты продемонстрировали
						высокий уровень технической подготовки и внимания к деталям. Кладка кирпичной стены требовала не только умения работать с материалами, но и
						творческого подхода для достижения эффекта «лофт», который я стремился реализовать в своём интерьере. Применение декоративной затирки придало стене
						особую текстуру и глубину, что сразу стало центральным элементом дизайна комнаты. Мастера использовали современные технологии, оставаясь верными
						традиционным методам, что обеспечило не только эстетичность, но и долговечность результата. На каждом этапе работы была возможность увидеть
						промежуточный результат, что позволило корректировать мелкие нюансы в реальном времени. Четкая организация работ, соблюдение сроков и постоянный
						обмен информацией сделали процесс сотрудничества максимально комфортным. Результатом стала уникальная стена, которая гармонично вписывается в общий
						интерьер и привлекает внимание всех гостей.
					</p>
					<p class="reviews__name">Мария Иванова</p>
					<p class="reviews__role">Дизайнер интерьеров</p>
				</div>
			</li>
			<li class="reviews__item keen-slider__slide">
				<div class="reviews__image">
					<img src="/img/reviews/3.webp" alt="" />
				</div>

				<div class="reviews__content">
					<p class="reviews__text">
						Работа по созданию авторской штукатурки стала для меня настоящим открытием в мире интерьерного дизайна. Проект предусматривал применение техники
						венецианской штукатурки, что требовало не только профессионального подхода, но и творческого взгляда на реализацию замысла. Команда специалистов
						проявила высокую квалификацию, подробно объяснив каждый этап процесса и предложив оптимальные решения для моего интерьера. Результатом стала гладкая
						фактура стен с глубоким, насыщенным блеском, который менялся в зависимости от освещения. Такое решение придало помещению особую атмосферу роскоши и
						уюта. Особое внимание уделялось подготовке поверхностей: мастера провели предварительную очистку и выравнивание стен, что обеспечило идеальное
						сцепление штукатурки с основанием. Благодаря профессионализму команды все работы были выполнены точно в срок и с соблюдением всех стандартов
						качества. Этот опыт убедил меня в том, что выбор данной компании был правильным, и я с уверенностью рекомендую их услуги всем, кто ценит качество и
						эстетику в ремонте.
					</p>
					<p class="reviews__name">Алексей Смирнов</p>
					<p class="reviews__role">Архитектор</p>
				</div>
			</li>
			<li class="reviews__item keen-slider__slide">
				<div class="reviews__image">
					<img src="/img/reviews/4.webp" alt="" />
				</div>

				<div class="reviews__content">
					<p class="reviews__text">
						Мой опыт полного ремонта квартиры площадью 120 м² превзошёл все ожидания. С самого начала работ команда продемонстрировала высокий уровень
						организации и профессионализма. Каждый этап – от демонтажа старых конструкций до финальной отделки – был четко спланирован и реализован в
						соответствии с предварительно утвержденным планом. Особое внимание уделялось подбору материалов, что гарантировало долговечность и высокое качество
						всех выполненных работ. Благодаря использованию современных технологий и инновационных подходов, ремонт прошёл быстро и без лишних заминок, что
						позволило мне минимизировать неудобства в период проведения работ. Мастера постоянно информировали меня о ходе работ, что создавало ощущение полного
						контроля и уверенности в результате. Интерьер квартиры был преобразован до неузнаваемости: современный дизайн, эргономичные решения и высокое
						качество отделочных работ сделали жилье уютным и функциональным. Результатом стала квартира, в которой каждая деталь продумана и выполнена с любовью
						и уважением к клиенту.
					</p>
					<p class="reviews__name">Елена Кузнецова</p>
					<p class="reviews__role">Риэлтор</p>
				</div>
			</li>
			<li class="reviews__item keen-slider__slide">
				<div class="reviews__image">
					<img src="/img/reviews/5.webp" alt="" />
				</div>

				<div class="reviews__content">
					<p class="reviews__text">
						Работа по монтажу деревянных панелей и выполнению декоративной резьбы стала для меня настоящим произведением искусства. От первых консультаций до
						финального этапа монтажа специалисты показали глубокое понимание работы с натуральным деревом и тонкостей художественной резьбы. Каждый элемент
						интерьера был проработан до мелочей, начиная от выбора породы дерева и заканчивая обработкой поверхности специальными составами для защиты и
						долговечности. Благодаря индивидуальному подходу и творческому взгляду мастеров, кабинет получил уникальный стиль, который органично вписывается в
						общий дизайн помещения. Процесс установки прошёл оперативно и качественно, без каких-либо задержек или компромиссов в отношении качества. Мне
						особенно запомнился момент, когда была выполнена сложная резьба по индивидуальному эскизу – работа мастеров поразила своей точностью и эстетической
						выразительностью. В результате получился не просто ремонт, а настоящее произведение искусства, которое придает интерьеру особый шарм и
						эксклюзивность.
					</p>
					<p class="reviews__name">Сергей Волков</p>
					<p class="reviews__role">Директор компании</p>
				</div>
			</li>
			<li class="reviews__item keen-slider__slide">
				<div class="reviews__image">
					<img src="/img/reviews/6.webp" alt="" />
				</div>

				<div class="reviews__content">
					<p class="reviews__text">
						Создание ванной комнаты в стиле «современная классика» стало для меня воплощением мечты о гармоничном сочетании современного дизайна и традиционных
						элементов. С самого начала проект отличался высоким уровнем организации, тщательной проработкой деталей и индивидуальным подходом к каждому клиенту.
						Специалисты предложили смелые, но в то же время очень практичные решения, позволившие создать пространство, отвечающее всем функциональным
						требованиям. Особое внимание было уделено выбору материалов: мрамор, высококачественная керамика и современные технологии сантехники сделали ванную
						не только красивой, но и долговечной. Каждый этап работ – от демонтажа до финальной отделки – выполнялся с соблюдением строгих стандартов качества,
						что гарантировало идеальный результат. Мастера детально обсуждали все нюансы проекта, учитывая мои пожелания и давая профессиональные советы по
						оптимизации пространства. Благодаря их стараниям, получилась ванная комната, которая не только радует глаз своей эстетикой, но и обеспечивает
						высокий уровень комфорта и безопасности.
					</p>
					<p class="reviews__name">Ольга Николаева</p>
					<p class="reviews__role">Блогер о дизайне</p>
				</div>
			</li>
		</ul>

		<nav class="reviews__nav">
			{#each Array(6) as _, index}
				<button class="reviews__bullet {index === currentSlide ? 'active' : ''}" onclick={() => bulletClick(index)}></button>
			{/each}
		</nav>
	</div>
</section>

<style lang="scss">
	.reviews {
		color: #ffffff;

		background-color: #ff6500;
		border-radius: rem(50);
		overflow: hidden;
		padding: rem(70) 0;

		/* .reviews__container */
		&__container {
		}
		/* .reviews__heading */
		&__heading {
			font-size: rem(40);
			font-weight: 600;

			margin-bottom: rem(50);
		}
		/* .reviews__items */
		&__items {
			display: flex;
			overflow: hidden;
		}
		/* .reviews__item */
		&__item {
			display: flex;
			gap: rem(40);

			padding: rem(40);
		}
		/* .reviews__image */
		&__image {
			flex: 0 0 rem(150);
			// width: rem(150);
			height: rem(150);

			img {
				width: 100%;
				height: 100%;
				object-fit: cover;
			}
		}
		/* .reviews__content */
		&__content {
			max-width: rem(800);
		}
		/* .reviews__text */
		&__text {
			font-size: rem(20);
			line-height: math.div(26, 20);

			margin-bottom: rem(20);
		}
		/* .reviews__name */
		&__name {
			margin-bottom: rem(5);
		}
		/* .reviews__role */
		&__role {
		}

		/* .reviews__nav */
		&__nav {
			display: flex;
			justify-content: center;
			gap: rem(15);
		}
		/* .reviews__bullet */
		&__bullet {
			width: rem(10);
			height: rem(10);
			background-color: #ffffff;
			border-radius: 50%;

			&.active {
				background-color: #ffb367;
			}
		}
	}
</style>

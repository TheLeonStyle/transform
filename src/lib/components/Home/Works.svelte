<section class="works">
	<div class="works__container">
		<h2 class="works__heading" data-aos="fade-up">Наши работы</h2>

		<ul class="works__items">
			<li class="works__item" data-aos="zoom-in">
				<div class="works__image">
					<img src="/img/works/1.webp" alt="" loading="lazy" />
				</div>
				<div class="works__content">
					<h3 class="works__title">Реставрация исторического фасада особняка</h3>
					<p class="works__subtitle">Комплексная реконструкция фасада здания 19 века. Сохранение лепнины, ручная работа, натуральные материалы</p>
				</div>
			</li>
			<li class="works__item" data-aos="zoom-in">
				<div class="works__image">
					<img src="/img/works/2.webp" alt="" loading="lazy" />
				</div>
				<div class="works__content">
					<h3 class="works__title">Кладка кирпичной стены с декоративной затиркой</h3>
					<p class="works__subtitle">Акцентная стена в интерьере квартиры. Эффект "лофт", ручная затирка, защита поверхности.</p>
				</div>
			</li>
			<li class="works__item" data-aos="zoom-in">
				<div class="works__image">
					<img src="/img/works/3.webp" alt="" loading="lazy" />
				</div>
				<div class="works__content">
					<h3 class="works__title">Авторская штукатурка в частном доме</h3>
					<p class="works__subtitle">Техника венецианской штукатурки. Глубина цвета, гладкая фактура, отражающий свет эффект.</p>
				</div>
			</li>
			<li class="works__item" data-aos="zoom-in">
				<div class="works__image">
					<img src="/img/works/4.webp" alt="" loading="lazy" />
				</div>
				<div class="works__content">
					<h3 class="works__title">Полный ремонт квартиры 120 м²</h3>
					<p class="works__subtitle">Все этапы — от демонтажа до финишной отделки. Чёткие сроки, прозрачная смета, один мастер на весь проект.</p>
				</div>
			</li>
			<li class="works__item" data-aos="zoom-in">
				<div class="works__image">
					<img src="/img/works/5.webp" alt="" loading="lazy" />
				</div>
				<div class="works__content">
					<h3 class="works__title">Монтаж деревянных панелей и резьбы</h3>
					<p class="works__subtitle">Ручная работа по дереву, оформление кабинета в частном доме. Натуральное дерево, лаконичный стиль.</p>
				</div>
			</li>
			<li class="works__item" data-aos="zoom-in">
				<div class="works__image">
					<img src="/img/works/6.webp" alt="" loading="lazy" />
				</div>
				<div class="works__content">
					<h3 class="works__title">Ванная комната в стиле "современная классика"</h3>
					<p class="works__subtitle">Мраморная укладка, скрытые коммуникации, дизайнерская сантехника. Всё под ключ.</p>
				</div>
			</li>
		</ul>
	</div>
</section>

<style lang="scss">
	.works {
		padding: rem(70) 0;

		/* .works__container */
		&__container {
		}
		/* .works__heading */
		&__heading {
			font-size: rem(40);
			font-weight: 600;
			text-align: center;

			margin-bottom: rem(50);
		}
		/* .works__items */
		&__items {
			display: grid;
			grid-template-columns: repeat(3, 1fr);
			gap: rem(20);
		}
		/* .works__item */
		&__item {
			display: flex;
			flex-direction: column;

			transition:
				transform 0.3s,
				box-shadow 0.3s;

			&:hover {
				transform: translateY(rem(-5));
			}
		}
		/* .works__image */
		&__image {
			width: 100%;
			height: rem(200);

			img {
				width: 100%;
				height: 100%;
				object-fit: cover;
			}
		}
		/* .works__content */
		&__content {
			flex: 1;
			background-color: #ffffff;
			border: rem(2) solid #dddddd;
			border-top: none;
			border-radius: 0 0 rem(10) rem(10);
			padding: rem(10) rem(20);
		}
		/* .works__title */
		&__title {
			font-size: rem(20);
			line-height: math.div(24, 20);
			color: #ff6500;
			font-weight: 600;

			margin-bottom: rem(10);
		}
		/* .works__subtitle */
		&__subtitle {
			font-size: rem(16);
			line-height: math.div(22, 16);
		}
	}
</style>

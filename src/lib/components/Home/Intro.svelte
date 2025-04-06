<section class="intro">
	<div class="intro__container">
		<div class="intro__content" data-aos="fade-down">
			<h1 class="intro__title" data-aos="fade-down">
				Вековые традиции - <span>современные технологии</span>
			</h1>
			<p class="intro__suptitle" data-aos="fade-down">Сообщество мастеров отделочников различной специализации, работа и цены без посредников</p>
			<a href="" class="intro__button">Наши услуги и цены</a>
		</div>

		<ul class="intro__items" data-aos="fade-down">
			<li class="intro__item" data-aos="fade-left">Офисы</li>
			<li class="intro__item" data-aos="fade-left">Дома</li>
			<li class="intro__item" data-aos="fade-left">Квартиры</li>
		</ul>
	</div>
</section>

<style lang="scss">
	.intro {
		background-image: url('/img/intro/bg.webp');
		background-position: center;
		background-size: cover;

		min-height: 100dvh;
		padding: rem(100) 0 rem(50);
		/* .intro__container */
		&__container {
			display: flex;
			align-items: center;
			gap: rem(40);

			padding: rem(80) rem(15) rem(80) rem(15); // ???
		}
		/* .intro__content */
		&__content {
			display: flex;
			flex-direction: column;
			gap: rem(40);
		}
		/* .intro__title */
		&__title {
			color: #ff6500;
			font-weight: 600;
			font-size: rem(60);
			line-height: math.div(70, 60);
			span {
				display: block;
			}
		}
		/* .intro__suptitle */
		&__suptitle {
			max-width: rem(550);

			font-size: rem(26);
			// font-weight: 600;
			line-height: math.div(32, 26);
		}
		/* .intro__button */
		&__button {
			align-self: start;

			color: #ffffff;
			font-weight: 600;

			background-color: #ff6500;
			border-radius: rem(30);
			padding: rem(15) rem(40);

			transition: background-color 0.3s ease 0s;

			&:hover {
				background-color: #ffb367;
			}
		}
		/* .intro__items */
		&__items {
			padding-left: rem(128);
			position: relative;
			&:before {
				content: '';
				position: absolute;
				left: 0;
				top: 50%;
				transform: translateY(-50%);

				width: 0;
				height: 0;
				border-top: rem(100) solid transparent;
				border-bottom: rem(100) solid transparent;
				border-left: rem(108) solid #ff6500;
			}
		}
		/* .intro__item */
		&__item {
			cursor: pointer; // ???
			font-size: rem(20);
			transition: color 0.3s ease 0s;

			&:not(:last-child) {
				margin-bottom: rem(30);
			}

			&:hover {
				color: #ff6500;
			}
		}
	}
</style>

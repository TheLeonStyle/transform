<header class="header">
	<div class="header__container">
		<a href="/" class="header__logo">
			<img src="/img/logo.svg" alt="Логотип" />
			<p data-aos="fade-left">
				Преображение <span>ремонтная артель</span>
			</p>
		</a>

		<nav class="header__nav" data-aos="fade-down">
			<a href="" class="header__link">Услуги</a>
			<a href="" class="header__link">Наши работы</a>
			<a href="" class="header__link">Отзывы</a>
			<a href="" class="header__link">Контакты</a>
		</nav>
	</div>
</header>

<style lang="scss">
	.header {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		z-index: 10;

		padding: rem(20) 0;
		/* .header__container */
		&__container {
			display: flex;
			align-items: center;
			justify-content: space-between;
			gap: rem(20);
		}
		/* .header__logo */
		&__logo {
			display: flex;
			align-items: center;
			gap: rem(10);
			img {
				width: rem(50);
				animation: rotate 10s linear infinite;
			}

			p {
				font-family: 'Miroslav', sans-serif;
				color: #ff6500;
				font-size: rem(18);
				font-weight: 600;
				line-height: math.div(20, 16);
				margin-top: rem(10);
			}

			span {
				display: block;
			}
		}
		/* .header__nav */
		&__nav {
			display: flex;
			align-items: center;
			gap: rem(60);
		}
		/* .header__link */
		&__link {
			color: inherit;
			font-size: rem(18);
			font-weight: 600;
			position: relative;
			transition: color 0.3s ease 0s;

			&:after {
				content: '';
				display: block;
				width: 0;
				height: rem(2);
				background-color: #ff6500;
				transition: width 0.3s ease 0s;
			}

			&:hover {
				color: #ff6500;

				&::after {
					width: 100%;
				}
			}
		}
	}

	@keyframes rotate {
		0% {
			transform: rotate(0deg);
		}
		100% {
			transform: rotate(360deg);
		}
	}
</style>

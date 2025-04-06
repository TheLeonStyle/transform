<footer class="footer">
	<div class="footer__container">
		<a href="/" class="footer__logo">
			<img src="/img/logo.svg" alt="Логотип" />
		</a>

		<div class="footer__info">
			<p class="footer__text">Адрес: Москва, Никольская 9</p>
			<p class="footer__text">© 2024-2025 Преображение.рф</p>
		</div>

		<div class="footer__socials">
			<a href="https://t.me/SkyFluxAgency" class="footer__social footer__icon icon-whatsapp" target="_blank"></a>
			<a href="http://wa.me/+79969139481" class="footer__social footer__icon icon-telegram" target="_blank"></a>
			<a href="tel:+7777777777" class="footer__social footer__icon icon-phone" target="_blank"></a>
		</div>
	</div>

	<p class="footer__developer">
		Разработка сайта: <a href="https://skyflux.ru" class="footer__developer" target="_blank">SkyFlux Agency</a>
	</p>
</footer>

<style lang="scss">
	.footer {
		background-color: #823400;
		padding: rem(10) 0;

		color: #ffffff;

		/* .footer__container */
		&__container {
			// display: flex;
			// justify-content: space-between;
			// align-items: center;
			display: grid;
			grid-template-columns: repeat(3, 1fr);
			align-items: center;
			gap: rem(10);
			margin-bottom: rem(10);
		}
		/* .footer__logo */
		&__logo {
			img {
				width: rem(50);
				height: rem(50);
				object-fit: cover;
			}
		}
		/* .footer__info */
		&__info {
			text-align: center;
		}
		/* .footer__text */
		&__text {
			margin-bottom: rem(5);
		}
		/* .footer__socials */
		&__socials {
			justify-content: end;
			display: flex;
			gap: rem(20);
		}
		/* .footer__social */
		&__social {
			font-size: rem(20);
			color: #ffffff;
			transition: color 0.3s ease 0s;
			&:hover {
				color: #ff6500;
			}
		}
		/* .footer__developer */
		&__developer {
			text-align: center;
			a {
				color: #ff6500;
				font-weight: 500;
			}
		}
	}
</style>

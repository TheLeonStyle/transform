<section class="contacts">
	<div class="contacts__container">
		<h2 class="contacts__heading">Контакты</h2>

		<ul class="contacts__items">
			<li class="contacts__item">
				<a href="tel:+7777777777" class="contacts__link contacts__icon icon-phone" target="_blank"></a>
			</li>
			<li class="contacts__item">
				<a href="https://vk.com/durov" class="contacts__link contacts__icon icon-vkontakte" target="_blank"></a>
			</li>
			<li class="contacts__item">
				<a href="http://wa.me/+79969139481" class="contacts__link contacts__icon icon-whatsapp active" target="_blank"></a>
			</li>
			<li class="contacts__item">
				<a href="https://t.me/SkyFluxAgency" class="contacts__link contacts__icon icon-telegram" target="_blank"></a>
			</li>
			<li class="contacts__item">
				<a href="mailto:skyflux2024@gmail.ru" class="contacts__link contacts__icon icon-gmail" target="_blank"></a>
			</li>
		</ul>
	</div>
</section>

<style lang="scss">
	.contacts {
		padding: rem(70) 0;
		/* .contacts__container */
		&__container {
		}
		/* .contacts__heading */
		&__heading {
			font-size: rem(40);
			font-weight: 600;
			text-align: center;

			margin-bottom: rem(50);
		}
		/* .contacts__items */
		&__items {
			display: flex;
			justify-content: center;
			align-items: center;
			gap: rem(40);
		}
		/* .contacts__item */
		&__item {
		}
		/* .contacts__link */
		&__link {
			display: flex;
			justify-content: center;
			align-items: center;
			width: rem(100);
			height: rem(100);
			background-color: #ffb367;
			border-radius: 50%;
			transition:
				width 0.3s ease 0s,
				height 0.3s ease 0s,
				font-size 0.3s ease 0s,
				background-color 0.3s ease 0s;

			position: relative;

			&::after {
				content: '';
				position: absolute;
				top: 50%;
				left: 50%;
				width: 100%;
				height: 100%;
				transform: translate(-50%, -50%) scale(1);
				border: rem(2) solid rgba(255, 101, 0, 0.5);
				border-radius: 50%;
				opacity: 0;
				animation: ripple 2s infinite;
				z-index: -1;
			}

			&.active,
			&:hover {
				width: rem(140);
				height: rem(140);

				font-size: rem(50);

				background-color: #ff6500;
			}
		}

		&__icon {
			color: #ffffff;
			font-size: rem(30);
		}
	}

	@keyframes ripple {
		0% {
			transform: translate(-50%, -50%) scale(1);
			opacity: 0.8;
		}
		100% {
			transform: translate(-50%, -50%) scale(1.4);
			opacity: 0;
		}
	}
</style>

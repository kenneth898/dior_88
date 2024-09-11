<template>
	<div style="height: 100%;" class="container-fluid">
		<div style="padding:10px ;" class="row ">
			<div class="col-6">
				<a :href="link + 'login'" rel="nofollow">
					<img width="100%" src="/image/login_btn.webp" alt="login">
				</a>
			</div>
			<div class="col-6">
				<a :href="link + 'en/sign-up'" rel="nofollow">
					<img width="100%" src="/image/register_btn.webp" alt="register">
				</a>
			</div>

			<!--balance-->
			<div class="col-6">
				<p>{{ $t('right.baki') }}</p>
				<p><b>0.00</b></p>
				<p>{{ $t('right.deposit') }}</p>
				<p><b>RM5.00</b></p>
				<p>{{ $t('right.withdraw') }}</p>
				<p><b>RM50.00</b></p>
			</div>
			<div class="col-6">
				<a :href="link + 'en/sign-up'" rel="nofollow">
					<img width="100%" src="/image/deposit_btn.webp" alt="deposit">
				</a>
				<a :href="link + 'en/sign-up'" rel="nofollow">
					<img width="100%" src="/image/withdraw_btn.webp" alt="withdraw">
				</a>
				<a :href="link + 'en/sign-up'" rel="nofollow">
					<img width="100%" src="/image/refresh_btn.webp" alt="refresh">
				</a>
			</div>

			<!--sport live-->
			<div class="col-12 bg_test">
				<div class="row right2">
					<div class="col-3 text_sportlive">
						<div class="image_col">
							<img width="90%" src="/image_webp/sportlive.webp" alt="sportlive1">
						</div>

						<p>{{ $t('right.manutd') }}</p>
					</div>
					<div class="col-6 text_sportlive">
						<p>{{ $t('right.starttime') }}</p>
						<p>17 Aug 2024</p>
						<p class="sportlive_text text_sportlive">03:00</p>
						<a :href="link + 'login'" class="betnow" rel="nofollow">{{
							$t('right.betnow') }}</a>
					</div>
					<div class="col-3 text_sportlive">
						<div class="image_col">
							<img width="90%" src="/image_webp/spo.webp" alt="sportlive2">
						</div>
						<p>{{ $t('right.fulham') }}</p>
					</div>
				</div>

				<div class="showmore_col">
					<a :href="link + 'en/sport-live/'" rel="nofollow">
						<p class="showmore">{{ $t('right.showmore') }}</p>
					</a>
				</div>

			</div>

			<div class="desktop">
				<a :href="link + 'en/sign-up'" rel="nofollow">
					<img style="border-radius: 10px;" width="100%" src="/image/free-credit-RM50_D.webp"
						alt="Download-APK-free-credit-RM50-D">
				</a>
			</div>

			<div class="mobile">
				<a :href="link + 'en/sign-up'" rel="nofollow">
					<img style="border-radius: 10px;" width="100%" src="/image/Download-APK-free-credit-RM50-M.webp"
						alt="Download-APK-free-credit-RM50-M">
				</a>
			</div>

		</div>
	</div>






</template>

<script>
import { mapGetters } from 'vuex';
export default {
	name: 'Right',
	computed: {
		...mapGetters(['link'])
	},
	mounted() {
		// 确保只有当链接不存在时才调用 fetchLink
		this.$store.dispatch('fetchLink');
	}
};
</script>

<style scoped>
.bg_test {
	align-content: center;
	background-image: url(/image_webp/right_bg2.webp);
	background-repeat: round;
	text-align: -webkit-center;
	width: 100%;
	margin-top: 10px;
	border-radius: 15px;
	padding-bottom: 10px;
	margin-bottom: 10px;
}

/* .bg_img {
	background: rgba(0, 0, 0, .3);
	border-right: 1px solid rgba(255, 255, 255, .5);
	height: 100vh;
} */

.right2 {
	margin-top: 25px;
	background-color: #FFF;
	border-radius: 10px;
	align-items: center;
	text-align: center;
	width: 100%;
}

.image_col {
	text-align: center;
}





.sportlive_col {
	padding: 26px 0px 10px 18px;
	text-align: -webkit-center;
	position: absolute;
}

.sportlive_text {
	font-size: 21px;
	color: #258D2D;
	font-family: digital-7;
}

.betnow {
	display: block;
	background: #4caf50;
	color: #fff;
	padding: 8px 0;
	line-height: 1;
	width: 72px;
	text-align: center;
	border-radius: 4px;
	margin: 5px auto 0;
	margin-bottom: 10px;
}

.showmore {
	background-color: #EEE;
	color: #000;
	text-align: center;
	padding: 8px;
	font-size: 13px;
	line-height: 1;
	border-radius: 5px;
	width: 100%;
	box-shadow: 0 0 3px rgb(0 0 0 / 30%);
	border: 1px solid #ccc;
	cursor: pointer;
}

.showmore_col {
	padding-top: 10px;
	margin-bottom: 10px;
}

@media screen and (max-width:770px) {


	.text_sportlive {
		font-size: 15px !important;
	}

	.betnow {
		font-size: 10px;
	}

	.sportlive_col {
		padding: 11px 0px 10px 22px !important;
	}
}

@media screen and (max-width:576px) {

	.sportlive_col {
		padding: 11px 0px 10px 25px !important;
	}
}

@media screen and (max-width:426px) {
	.sportlive_col {
		padding: 30px 0px 10px 25px !important;
	}

	.text_sportlive {
		font-size: 14px !important;
	}
}

a {
	text-decoration: none;
}

@media screen and (max-width:376px) {

	.sportlive_col {
		padding: 22px 0px 10px 25px !important;
	}
}

p {
	margin: 0px;
}

.mobile {
	display: none;
}

.desktop {
	padding: 0px;
}

@media screen and (max-width:768px) {
	.desktop {
		display: none;
	}

	.mobile {
		display: block;
		padding: 0px;

	}

	.srceen_mobile {
		padding: 10px;
	}
}
</style>

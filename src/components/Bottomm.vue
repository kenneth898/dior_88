<template>
	<div class="container-fluid">
		<div class="row">
			<nav class="navbar fixed-bottom">
				<div class="container-fluid d-flex justify-content-center">


					<div class="menu d-flex justify-content-around w-100">

						<div class="nav-item d-flex flex-column align-items-center text-center column-height">
							<a :href="link" class="nav-link" rel="nofollow" alt="Home" target="_blank">
								<img class="nav-icon img1" src="/image/home_btn.webp" alt="Home"></a>
						</div>

						<div class="nav-item d-flex flex-column align-items-center text-center column-height">
							<a :href="link + 'en/sign-up'" class="nav-link" rel="nofollow" target="_blank">
								<img class="nav-icon img2" src="/image/history_btn.webp" alt="History"></a>
						</div>

						<div class="nav-item d-flex flex-column align-items-center text-center column-height">
							<a :href="link + 'en/sign-up'" class="nav-link" rel="nofollow" alt="bonus" target="_blank">
								<img class="nav-icon img3" src="/image/promotion_btn.webp" alt="Promo"></a>
						</div>
						<div class="nav-item d-flex flex-column align-items-center text-center column-height">
							<a :href="link + 'en/sign-up'" class="nav-link" rel="nofollow" alt="history"
								target="_blank">
								<img class="nav-icon img4" src="/image/livechat_btn.webp" alt="Live Chat"></a>
						</div>


						<div class="nav-item d-flex flex-column align-items-center text-center column-height">
							<a :href="link + 'en/sign-up'" class="nav-link" rel="nofollow" alt="setting"
								target="_blank">
								<img class="nav-icon img5" src="/image/setting_btn.webp" alt="Setting"></a>
						</div>

					</div>
				</div>
			</nav>
		</div>
	</div>
</template>

<script>
import { mapGetters } from 'vuex';
export default {
	name: 'bottom',
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
.img1 {
	width: 48%;
}

.img2 {
	width: 48%;
}

.img3 {
	width: 48%;
}

.img4 {
	width: 48%;
}

.img5 {
	width: 48%;
}

.navbar.fixed-bottom {
	background-image: url('/image/bottom_bg.webp');
	height: 5%;
	background-size: cover;
}

.nav-item {
	flex: 1;
}

.menu {
	position: relative;
	top: -10px;
	align-items: end;

}

.column-height {
	position: relative;
	height: 40%;
}

@media screen and (max-width: 2560px) {
	.navbar.fixed-bottom {
		height: 9%;
	}
}

@media screen and (max-width: 1600px) {
	.column-height {
		height: 25%;
	}
}

@media screen and (max-width: 768px) {
	.menu {
		top: -8px !important;
	}

	.img1 {
		width: 40% !important;
	}

	.img2 {
		width: 40% !important;
	}

	.img3 {
		width: 40% !important;
	}

	.img4 {
		width: 40% !important;
	}

	.img5 {
		width: 40% !important;
	}
}

@media screen and (max-width:576px) {
	.navbar.fixed-bottom {
		height: 10% !important;
	}

	.menu {
		top: -5px !important;
	}

	.img1 {
		width: 65% !important;
	}

	.img2 {
		width: 65% !important;
	}

	.img3 {
		width: 65% !important;
	}

	.img4 {
		width: 65% !important;
	}

	.img5 {
		width: 65% !important;
	}
}
</style>

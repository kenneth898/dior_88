<template>
	<div class="container-fluid">
		<div class="col-12 ">
			<div class="row ">
				<div class="bg_img">
					<!--owl carousel-->
					<div id="carouselExampleInterval" class="carousel slide" data-bs-ride="carousel">
						<div class="carousel-inner">
							<div class="carousel-item active" data-bs-interval="2000">
								<a :href="link + 'en/sign-up'" rel="nofollow">
									<img width="100%" src="/image/banner1.webp" class="d-block w-100" alt="banner1">
								</a>
							</div>
							<div class="carousel-item" data-bs-interval="2000">
								<a :href="link + 'en/sign-up'" rel="nofollow">
									<img width="100%" src="/image/banner2.webp" class="d-block w-100" alt="banner2">
								</a>
							</div>
							<div class="carousel-item" data-bs-interval="2000">
								<a :href="link + 'en/sign-up'" rel="nofollow">
									<img width="100%" src="/image/banner3.webp" class="d-block w-100" alt="banner3">
								</a>
							</div>
						</div>

						<div class="bonus">
							<a :href="link + 'en/sign-up'" rel="nofollow">
								<img style="border-radius:10px ;" width="100%" src="/image/bonus388.webp"
									alt="bonus388">
							</a>
						</div>

						<div class="srceen_mobile">
							<div class="mobile">
								<a :href="link + 'en/sign-up'" rel="nofollow">
									<img style="border-radius:10px ;" width="100%"
										src="/image/Daily_unlimited_bonus_M.webp" alt="Daily_unlimited_bonus_M">
								</a>
							</div>
							<!--button bg-->
							<div class="btn_bg">
								<a :href="link + 'en/sign-up'" rel="nofollow">
									<img width="100%" src="/image/btn_bg.webp" alt="btn_bg">
								</a>

								<div style="position: absolute; bottom: 9px;" class="row">
									<div class="col-6 btn_left">
										<a :href="link + 'en/sign-up'" rel="nofollow">
											<img width="95%" src="/image/share_btn.webp" alt="share">
										</a>
									</div>
									<div class="col-6 btn_right">
										<a :href="link + 'en/sign-up'" rel="nofollow">
											<img width="95%" src="/image/downline_btn.webp" alt="downline">
										</a>
									</div>
									<div class="col-6 btn_left">
										<a :href="link + 'en/sign-up'" rel="nofollow">
											<img width="95%" src="/image/copy_btn.webp" alt="copy">
										</a>
									</div>
									<div class="col-6 btn_right">
										<a :href="link + 'en/sign-up'" rel="nofollow">
											<img width="95%" src="/image/more_btn.webp" alt="more">
										</a>
									</div>

								</div>
							</div>

							<div class="desktop">
								<a :href="link + 'en/sign-up'" rel="nofollow">
									<img style="border-radius:10px ;" width="100%"
										src="/image/Daily_unlimited_bonus_D.webp" alt="Daily_unlimited_bonus_D">
								</a>
							</div>


						</div>


					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import { mapGetters } from 'vuex';
export default {

	name: 'Left',
	methods: {
		setActive(index, componentId) {
			this.activeIndex = index;
			this.scrollTo(componentId);
		},
		scrollTo(id) {
			const element = document.getElementById(id);
			if (element) {
				element.scrollIntoView({ behavior: 'smooth' });
			}
		},
	},
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
@media screen and (max-width:770px) {

	.carousel {
		padding-top: 0px !important;
	}

	.bg_img {
		padding: 0px !important;
	}
}

.carousel {
	padding-top: 10px;
}


.btn_bg {
	position: relative;
	padding-top: 10px;
}

.btn_left {
	text-align-last: end;
	padding-right: 0px;
}

.btn_right {
	text-align-last: start;
	padding-left: 0px;
}

.desktop {
	padding-top: 10px;
}

.mobile {
	display: none;
}

@media screen and (max-width:768px) {
	.desktop {
		display: none;
	}

	.mobile {
		display: block;
	}

	.srceen_mobile {
		padding: 10px;
	}

	.bonus {
		padding: 10px;
	}
}

.bonus {
	padding-top: 10px;
}
</style>
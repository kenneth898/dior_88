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
import axios from 'axios';
export default {

	name: 'Left',
	data() {
		return {
			link: ""
		}
	},
	methods: {
		async calllink() {
			try {
				const response = await axios.get('https://seo.mobileapplab.online/api/atas?fields[0]=ataskasino_com', {
					headers: {
						"Authorization": "Bearer " + "1c4db3188ab2e9a077928920d9cc8d3322d15f9751bc2054a5cb70008df79cf3e3a4dd005a75a1f2db40eb953292ee10ef699693e96e9d77a98439f438ee6a6e6805a8a955e992f082b9e6118a4345e1ed18438ff9789edf9ed1dd58af45ee6669a7519a1291746959ff45bc2054b7f408b5da5ea8cd04d588a2704b7e218021",
					}
				});
				this.link = response.data.data.attributes.ataskasino_com;

				console.log(this.link);
			} catch (error) {
				console.error(error);
			}
		},
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
	mounted() {
		this.calllink();
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
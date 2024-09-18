<template>
	<div class="container-fluid">
		<div class="col-12">
			<div class="row">
				<div style="padding: 0px;" class="col-sm-12 col-md-3">
					<!--left-->

					<div class=" left">
						<div class="leftright_bg">
							<Left />
						</div>

					</div>
				</div>

				<div style="padding: 0px;" class="col-sm-12 col-md-6 mobile_col2 center_col">
					<!--main-->
					<div class="nav nav-pills">
						<a style="padding: 0px;" v-for="(item, index) in menuItems" :key="index"
							:class="['nav-link', { active: activeIndex === index }]"
							@click="setActive(index, item.componentId)">
							<img :src="activeIndex === index ? item.activeSrc : item.inactiveSrc" :alt="item.name"
								class="img-fluid" />
						</a>
					</div>
					<component :is="currentComponent"></component>

					<div style="padding-bottom: 100px;" class="content" :id="menuItems[activeIndex].componentId">
						<Content />
					</div>

					<div class="icon_col">
						<a :href="link + 'en/sign-up'" rel="nofollow">
							<img width="100%" src="/image/download_app.webp" alt="download">
						</a>

						<a href="https://t.me/atas77channel" rel="nofollow">
							<img width="100%" src="/image/subscribe_us.webp" alt="subscribe">
						</a>

						<a :href="link + 'en/sign-up'" rel="nofollow">
							<img width="100%" src="/image/follow_us.webp" alt="facebook">
						</a>
					</div>
				</div>






				<div style="padding: 0px;" class="col-sm-12 col-md-3 mobile_col">
					<!--right-->
					<div class="right">
						<div class="right_bg">
							<Right />
						</div>
					</div>
				</div>

			</div>
		</div>

		<div style="padding-top: 10px;">
			<Notice />
		</div>
	</div>
</template>

<script>
import Left from '../components/Left.vue';
import Right from '../components/Rightt.vue';
import Menu1 from '../components/contenttt.vue';
import Content from '@/components/Menuu.vue';
import Notice from '@/components/noticee.vue';
import { mapGetters } from 'vuex';

export default {
	name: 'Home',
	components: {
		Left,
		Right,
		Menu1,
		Content,
		Notice
	},
	data() {
		return {
			activeIndex: 0,
			menuItems: [
				{ name: 'Menu 1', activeSrc: '/image_webp/advanplay_active.webp', inactiveSrc: '/image_webp/advanplay_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 2', activeSrc: '/image_webp/jili_active.webp', inactiveSrc: '/image_webp/jili_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 3', activeSrc: '/image_webp/rich_active.webp', inactiveSrc: '/image_webp/rich_no_active.webp', component: 'Menu1', componentId: 'menu1' },

				{ name: 'Menu 4', activeSrc: '/image_webp/bongo_active.webp', inactiveSrc: '/image_webp/bongo_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 5', activeSrc: '/image_webp/pragmatic_active.webp', inactiveSrc: '/image_webp/pragmatic_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 6', activeSrc: '/image_webp/playtech_active.webp', inactiveSrc: '/image_webp/playtech_no_active.webp' },

				{ name: 'Menu 7', activeSrc: '/image_webp/cewin_active.webp', inactiveSrc: '/image_webp/cewin_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 8', activeSrc: '/image_webp/jdb_active.webp', inactiveSrc: '/image_webp/jdb_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 9', activeSrc: '/image_webp/dragoon_active.webp', inactiveSrc: '/image_webp/dragoon_no_active.webp', component: 'Menu1', componentId: 'menu1' },

				{ name: 'Menu 10', activeSrc: '/image_webp/rich88_active.webp', inactiveSrc: '/image_webp/rich88_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 11', activeSrc: '/image_webp/bigpot_active.webp', inactiveSrc: '/image_webp/bigpot_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 12', activeSrc: '/image_webp/slot_active.webp', inactiveSrc: '/image_webp/slot_no_active.webp', component: 'Menu1', componentId: 'menu1' },

				{ name: 'Menu 13', activeSrc: '/image_webp/live_active.webp', inactiveSrc: '/image_webp/live_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 14', activeSrc: '/image_webp/sport_active.webp', inactiveSrc: '/image_webp/sport_no_active.webp', component: 'Menu1', componentId: 'menu1' },
				{ name: 'Menu 15', activeSrc: '/image_webp/other_active.webp', inactiveSrc: '/image_webp/other_no_active.webp', component: 'Menu1', componentId: 'menu1' },
			],
		};
	},
	computed: {
		...mapGetters(['link']),
		currentComponent() {
			return this.menuItems[this.activeIndex].component;
		}
	},
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
	mounted() {
		this.$store.dispatch('fetchLink');
	}
};
</script>

<style scoped>
.center_col {
	background-image: url('/image/pink_bg.webp');
}


.leftright_bg {
	background: rgba(0, 0, 0, .3);
	height: 100%;
	border-right: 1px solid rgba(255, 255, 255, .5);
}

.left {
	height: 100%;
	background-image: url('/image/pink_bg.webp');

}

.right_bg {
	background: rgba(0, 0, 0, .3);
	height: 100%;
	border-left: 1px solid rgba(255, 255, 255, .5);
}

.right {
	height: 100%;
	background-image: url('/image/pink_bg.webp');
}


@media (max-width: 768px) {

	.leftright_bg {
		background: rgba(0, 0, 0, 0);
		height: 100%;
		border-right: 0px solid rgba(255, 255, 255, .5);
	}

	.right_bg {
		background: rgba(0, 0, 0, 0);
		height: 100%;
		border-left: 0px solid rgba(255, 255, 255, .5);
	}

	.nav-pills {
		display: flex;
		overflow-x: auto;
		/* 启用水平滚动 */
		white-space: nowrap;
		/* 防止换行 */
		padding: 0;
	}

	.nav-link {
		flex: 0 0 auto;
		/* 确保菜单项不变形 */
		width: 20%;
		/* 每个菜单项的宽度，假设有5个菜单项 */
		text-align: center;
		padding: 0;
	}
}

.icon_col {
	display: flex;
	flex-direction: column;
	width: 20px;
	position: fixed;
	bottom: 100px;
	right: 0px;
}



.icon {
	display: grid;
	position: absolute;
	gap: 0.5rem;
}

.nav-item {
	font-weight: bolder;
}

.nav-pills {
	--bs-nav-pills-link-active-bg: none;
	display: flex;
	flex-wrap: nowrap;
	padding: 10px 10px 10px 10px;

}


.nav-link.active {
	border-radius: 30px;
}

.menu_col {
	padding-bottom: 10px;
}

.main-col {
	display: grid;
	grid-template-columns: repeat(6, 1fr);
	justify-items: center;
	gap: 0.5rem;
}

.main-col img {
	width: 90%;
}

@media screen and (max-width:768px) {
	.main-col {
		grid-template-columns: repeat(3, 1fr);
	}


}

@media screen and (max-width:767px) {
	.mobile_col {
		order: 2;
	}

	.mobile_col2 {
		order: 3;
	}
}

.content {
	padding-left: 12px;
	padding-right: 12px;
}

h1 {
	font-size: 25px;
	font-weight: bolder;
}

h2 {
	font-size: 23px;
	font-weight: bolder;
}

h3 {
	font-size: 15px;
	font-weight: bolder;
}

.icon_col {
	display: flex;
	flex-direction: column;
	width: 20px;
	position: fixed;
	bottom: 120px;
	right: 0px;
}
</style>

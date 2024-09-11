<template>
	<div class="main-col container">
		<div v-for="(image, index) in images" :key="index" class="col">
			<a :href="link + 'en/sign-up'" rel="nofollow">
				<img :src="`/main_image/${image.fileName}.webp`" :alt="image.fileName" class="img-fluid">
				<p>{{ $t('menu.play') }}</p>
			</a>
		</div>
	</div>
</template>

<script>
import { mapGetters } from 'vuex';
export default {
	name: 'Menu1',
	data() {
		return {
			images: [
				{ fileName: '1_kingyo_riches' },
				{ fileName: '2_fish_prawncrab_bonanza' },
				{ fileName: '3_ramakien_blessing' },
				{ fileName: '4_firefly_hunter' },
				{ fileName: '5_dark_ritual' },
				{ fileName: '6_hungry_slime' },
				{ fileName: '7_aztec2' },
				{ fileName: '8_football_fever' },
				{ fileName: '9_crazy_bounty' },
				{ fileName: '10_dragon_chis_quest' },
				{ fileName: '11_maya_elemental_totem' },
				{ fileName: '12_xiang_qi_ways2' },
				{ fileName: '13_aztec_bonus_hunt' },
				{ fileName: '14_last_samurai' },
				{ fileName: '15_genie_myscery' },
				{ fileName: '16_disco777' },
				{ fileName: '17_world_cup' },
				{ fileName: '18_boom_of_prosperity' },
				{ fileName: '19_astro_bunny' },
				{ fileName: '20_cookie_hunter' },
				{ fileName: '21_xmas_gift_delight' },
				{ fileName: '22_mace_of_hercules' },
				{ fileName: '23_wheel_of_gems' },
				{ fileName: '24_scale_of_heaven_anubis' },
				{ fileName: '25_infinity_ocean' },
				{ fileName: '26_dj_fever' },
				{ fileName: '27_jewel_mastermind' },
				{ fileName: '28_pubg2' },
				{ fileName: '29_fantastic_beast' },
				{ fileName: '30_slotto_4d' },
				{ fileName: '31_xiang_qi_ways' },
				{ fileName: '32_candy_rush' },
				{ fileName: '33_fortune_gods_pot' },
				{ fileName: '34_angient_gems' },
				{ fileName: '35_tiger_on_gold' },
				{ fileName: '36_hu_fu_blessing' },
				{ fileName: '37_battle_of_heroes' },
				{ fileName: '38_mine_of_prosperity' },
				{ fileName: '39_eye_of_ra' },
				{ fileName: '40_ninja_legend' },
				{ fileName: '41_treasure_of_drake' },
				{ fileName: '42_immortal_love' },
				{ fileName: '43_racing_for_luck' },
				{ fileName: '44_treasure_guardian' },
				{ fileName: '45_fortunes_warrior' },
				{ fileName: '46_chronicle_of_heroes_3wariords' },
				{ fileName: '47_chronicle_of_heroes_lucky_dragon' },
				{ fileName: '48_king_of_glory' },
				{ fileName: '49_bombombot' },
				{ fileName: '50_counter_terrorists' },
				{ fileName: '51_bubble_dragon' },
				{ fileName: '52_road_to_uefa' },
				{ fileName: '53_bobo_monster' },
				{ fileName: '54_chronicle_of_heroes_divine_tree' },
				{ fileName: '55_road_to_euro' }
			],

		};
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
.main-col {
	display: grid;
	grid-template-columns: repeat(6, 1fr);
	justify-items: center;
	gap: 0.5rem;
	text-align: center;
	text-align: -webkit-center;
}

@media screen and (max-width: 768px) {
	.main-col {
		grid-template-columns: repeat(3, 1fr);
	}
}

a {
	text-decoration: none;
}

p {
	padding: 5px;
	margin-top: 5px;
	width: 100%;
	color: #fff;
	background-color: #a0141d;
	border-radius: 30px;
	padding: 3px 0;
	margin-top: 8px;
	font-size: 11px;
}

img {
	border-radius: 10px;
	border: 1px solid #fff;
	background-color: #fff;
}
</style>

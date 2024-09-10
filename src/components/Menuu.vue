<template>
	<h3>
		{{ $t('content1.1') }}|
		{{ $t('content1.2') }}|
		{{ $t('content1.3') }}
	</h3>
	<p>
		{{ $t('text.1') }}
		<a style="font-weight: 900; color:#800000;" href="https://www.dior88.info/">
			{{ $t('text.2') }}</a>
		{{ $t('text.3') }}
		<b>{{ $t('text.4') }}</b>
		{{ $t('text.5') }}
	</p>
	<br>
	<p>
		{{ $t('text.6') }}
		<b>{{ $t('text.7') }}</b>
		{{ $t('text.8') }}
	</p>
	<br>
	<h3>
		{{ $t('wheretostart.title') }}
	</h3>
	<p>
		{{ $t('wheretostart.1') }}
		<b> {{ $t('wheretostart.2') }}</b>
		{{ $t('wheretostart.3') }}
	</p>
	<br>
	<ol>
		<li>
			{{ $t('wheretostart.4') }}
			<b>{{ $t('wheretostart.5') }}</b>
			{{ $t('wheretostart.6') }}
		</li>
		<li>
			{{ $t('wheretostart.7') }}
		</li>
		<li>
			{{ $t('wheretostart.8') }}
			<b>{{ $t('wheretostart.9') }}</b>
			{{ $t('wheretostart.10') }}
		</li>
	</ol>
	<br>
	<p>{{ $t('wheretostart.11') }}</p>
	<br>
	<h3>
		{{ $t('ewalletcasionotransfer.title') }}
	</h3>
	<p>
		{{ $t('ewalletcasionotransfer.1') }}
		<b>{{ $t('ewalletcasionotransfer.2') }}</b>
		{{ $t('ewalletcasionotransfer.3') }}
		<b>{{ $t('ewalletcasionotransfer.4') }}</b>
		{{ $t('ewalletcasionotransfer.5') }}
	</p>
	<br>
	<h3>
		{{ $t('onlinemalysia.title') }}
	</h3>
	<p>
		{{ $t('onlinemalysia.1') }}
		<b>{{ $t('onlinemalysia.2') }}</b>
		{{ $t('onlinemalysia.3') }}
	</p>
	<ul>
		<li>
			<b>{{ $t('onlinemalysia.4') }}</b>
			{{ $t('onlinemalysia.5') }}
		</li>
		<li>
			<b>{{ $t('onlinemalysia.6') }}</b>
			{{ $t('onlinemalysia.7') }}
		</li>
		<li>
			<b>{{ $t('onlinemalysia.8') }}</b>
			{{ $t('onlinemalysia.9') }}
		</li>
	</ul>
	<br>
	<p>
		{{ $t('onlinemalysia.10') }}
		<b>{{ $t('onlinemalysia.11') }}</b>
		{{ $t('onlinemalysia.12') }}
	</p>
	<br>
	<h3>
		{{ $t('casinoapp.title') }}
	</h3>
	<p>
		{{ $t('casinoapp.1') }}
		<b>{{ $t('casinoapp.2') }}</b>
		{{ $t('casinoapp.3') }}
	</p>


	<a href="//www.dmca.com/Protection/Status.aspx?ID=bd071465-17bf-4b90-b6e5-d51ffeb2271e"
		title="DMCA.com Protection Status" class="dmca-badge"> <img
			src="https://images.dmca.com/Badges/dmca_copyright_protected150c.png?ID=bd071465-17bf-4b90-b6e5-d51ffeb2271e"
			alt="DMCA.com Protection Status" /></a>


	<p style="font-weight: 700;">
		{{ $t('Footer.title') }}
	</p>

	<p>
		{{ $t('Footer.1') }}
		| <a :href="link" style="font-weight: 900; color:#800000;">{{ $t('Footer.2') }}</a> |
		{{ $t('Footer.3') }}
		<a :href="link"><b>{{ $t('Footer.4') }}</b></a>
		{{ $t('Footer.5') }}
	</p>

	<p>
		{{ $t('Footer.6') }}|
		{{ $t('Footer.7') }}|
		{{ $t('Footer.8') }}
		<a :href="link2" style="font-weight: 900; color:#800000;">{{ $t('Footer.9') }}</a>
		{{ $t('Footer.10') }}
		<a :href="link2"><b>{{ $t('Footer.11') }}</b></a>
		{{ $t('Footer.12') }}
	</p>



</template>
<script>
import axios from 'axios';
export default {
	name: 'Content',
	data() {
		return {
			link: "",
			link2: ""
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
		async calllink2() {
			try {
				const response = await axios.get('https://seo.mobileapplab.online/api/atas?fields[0]=atascasinobet_com', {
					headers: {
						"Authorization": "Bearer " + "1c4db3188ab2e9a077928920d9cc8d3322d15f9751bc2054a5cb70008df79cf3e3a4dd005a75a1f2db40eb953292ee10ef699693e96e9d77a98439f438ee6a6e6805a8a955e992f082b9e6118a4345e1ed18438ff9789edf9ed1dd58af45ee6669a7519a1291746959ff45bc2054b7f408b5da5ea8cd04d588a2704b7e218021",
					}
				});
				this.link2 = response.data.data.attributes.atascasinobet_com;

				console.log(this.link2);
			} catch (error) {
				console.error(error);
			}
		},
	},
	mounted() {
		this.calllink();
		this.calllink2();
	}
}
</script>
<style>
h1 {
	font-size: 25px !important;
	font-weight: bolder !important;
}

h2 {
	font-size: 23px !important;
	font-weight: bolder !important;
}

h3 {
	font-size: 18px !important;
	font-weight: bolder !important;
}
</style>

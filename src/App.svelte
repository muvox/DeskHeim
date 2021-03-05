<script>
	import { fade } from 'svelte/transition';
	import {onMount, onDestroy} from 'svelte'
	import { dataset_dev } from 'svelte/internal'
	import Panel1 from './Panel1.svelte'
	import Panel2 from './Panel2.svelte'
	import Panel3 from './Panel3.svelte'
	import Panel4 from './Panel4.svelte'

	const fetchData = (async () => {
		const response = await fetch('http://192.168.1.151:3000/')
		console.log('reponse', response)
		return await response.json()
	})()

</script>

<main style="background-color: #6C7C99">


		<p class="text-pop-up-top" style="font-size: 500%; margin-top: 30px; margin-bottom: 0px;">ᛗ</p>
		<div class="wrapper">
			<div class="one">
				{#await fetchData}
					<p class="fade-in" style="font-size: 500%; margin-top: 30px;margin-bottom: 20px;">ᛗ</p>
					<p> fetching server data</p>
				{:then payload}
					<Panel1 data={payload}/>
				{:catch error}
					<p> Error occured! </p>
				{/await}
			</div>
			<div class="two">
				{#await fetchData}
					<p class="fade-in" style="font-size: 500%; margin-top: 30px;margin-bottom: 20px;">ᛗ</p>
					<p> fetching server data</p>
				{:then payload}
					<Panel2 data={payload}/>
				{:catch error}
					<p> Error occured! </p>
				{/await}

			</div>
			<div class="three">
				{#await fetchData}
					<p class="fade-in" style="font-size: 500%; margin-top: 30px;margin-bottom: 20px;">ᛗ</p>
					<p> fetching server data</p>
				{:then payload}
					<Panel3 data={payload}/>
				{:catch error}
					<p> Error occured! </p>
				{/await}

			</div>
			<div class="four">
				{#await fetchData}
					<p class="fade-in" style="font-size: 500%; margin-top: 30px;margin-bottom: 20px;">ᛗ</p>
					<p> fetching server data</p>
				{:then payload}
					<Panel4 data={payload}/>
				{:catch error}
					<p> Error occured! </p>
				{/await}

			</div>
		</div>

</main>

<style>
	.wrapper{
		display: grid;
		grid-template-columns: repeat(8, 1fr);
		column-gap: 15px;
		row-gap: 15px;
		grid-auto-rows: 120px;
		grid-template-areas:
			"a a a a b b b b"
			"a a a a b b b b"
			"c c c c d d d d"
			"c c c c d d d d";
		align-items: start;
		min-width: 100%;
		min-height: 100%;
	}
	@media (max-width: 700px) {
		.wrapper{
			display: flex;
			flex-direction: column;
			align-items: start;
			min-width: 100%;
			min-height: 100%;
		}
	}
	.one {
		grid-area: a;
		background-color: #99a6c0;
		border-radius: 3px;		
		width: 100%;
		height: 100%
	}
	.two {
		grid-area: b;
		border-radius: 3px;
		background-color: #99a6c0;
		width: 100%;
		height: 100%;
	}
	.three {
		grid-area: c;
		border-radius: 3px;
		background-color: #99a6c0;
		width: 100%;
		height: 100%;

	}
	.four {
		grid-area: d;
		border-radius: 3px;
		background-color: #99a6c0;
		width: 100%;
		height: 100%;

	}
	:global(body) {
		background-color: #6c7b99;
	}
	.fade-in {
		animation: fadeIn ease 2s infinite;
		-webkit-animation: fadeIn ease 2s infinite;
		-moz-animation: fadeIn ease 2s infinite;
		-o-animation: fadeIn ease 2s infinite;
		-ms-animation: fadeIn ease 2s infinite;
	}

	div {
		border-radius: 4px;
	}
	@keyframes fadeIn{
		0% {opacity:0;}
		50% {opacity:1;}
		100% {opacity:0;}
	}

	@-moz-keyframes fadeIn {
		0% {opacity:0;}
		50% {opacity:1;}
		100% {opacity:0;}
	}

	@-webkit-keyframes fadeIn {
		0% {opacity:0;}
		50% {opacity:1;}
		100% {opacity:0;}
	}

	@-o-keyframes fadeIn {
		0% {opacity:0;}
		50% {opacity:1;}
		100% {opacity:0;}
	}

	@-ms-keyframes fadeIn {
		0% {opacity:0;}
		50% {opacity:1;}
		100% {opacity:0;}
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	:body(p) {
		color: #eeeeed;
	}


	main {
		max-width: 100%;
	}

	.text-pop-up-top{-webkit-animation:text-pop-up-top 1s both;animation:text-pop-up-top 1s both}
	@-webkit-keyframes text-pop-up-top{0%{-webkit-transform:translateY(0);transform:translateY(0);-webkit-transform-origin:50% 50%;transform-origin:50% 50%;text-shadow:none}100%{-webkit-transform:translateY(-50px);transform:translateY(-50px);-webkit-transform-origin:50% 50%;transform-origin:50% 50%;text-shadow:0 1px 0 #ccc,0 2px 0 #ccc,0 3px 0 #ccc,0 4px 0 #ccc,0 5px 0 #ccc,0 6px 0 #ccc,0 7px 0 #ccc,0 8px 0 #ccc,0 9px 0 #ccc,0 50px 30px rgba(0,0,0,.3)}}@keyframes text-pop-up-top{0%{-webkit-transform:translateY(0);transform:translateY(0);-webkit-transform-origin:50% 50%;transform-origin:50% 50%;text-shadow:none}100%{-webkit-transform:translateY(-50px);transform:translateY(-50px);-webkit-transform-origin:50% 50%;transform-origin:50% 50%;text-shadow:0 1px 0 #ccc,0 2px 0 #ccc,0 3px 0 #ccc,0 4px 0 #ccc,0 5px 0 #ccc,0 6px 0 #ccc,0 7px 0 #ccc,0 8px 0 #ccc,0 9px 0 #ccc,0 50px 30px rgba(0,0,0,.3)}}
</style>

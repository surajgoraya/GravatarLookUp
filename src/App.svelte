<script>
	import md5 from "md5";
	import {fade} from 'svelte/transition';
    import Top from "./components/Top.svelte";
    import Footer from "./components/Footer.svelte";
	
	let email = ''
	$: hash = email == '' ? '' : md5(email.toLowerCase());
	$: avURL = `https://www.gravatar.com/avatar/${hash}?s=1024`;

	const handleEmailChange = (e) => {
		if (e.key == 'Enter'){
			let val = e.target.value;
			email = val;
		}
	}
</script>

<main>
	<Top/>
	<p>Look up and get any <a href="https://en.gravatar.com/">Gravatar</a></p>
	<div class="get-area">
		<hr/>
		<p class="muted">Press <kbd>enter</kbd> on your keyboard to get the Gravatar</p>
		<input placeholder="example@example.com" type="email" on:keydown={handleEmailChange}/>
	</div>
	<div class="avatar">
		{#if hash != ''}
			<img src={avURL} alt={`${email}'s Gravatar Avatar.`} transition:fade/>
			
			<br/>
			{#if email !== '' } <div class="avatar__addInfo"><p class="md5">MD5 Hash: <code>{hash}</code></p><a href={`https://www.gravatar.com/avatar/${hash}?s=2048`} target="_blank">Full Res Image&nbsp;<i class="bi bi-box-arrow-up-right"></i></a></div> {/if}
		{/if}
	</div>
	<Footer/>
</main>

<style>
	.avatar {
		margin-top: 2rem;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.avatar__addInfo {
		display: flex;
		flex-direction: column-reverse;
		justify-content: center;
		align-items: center;
		gap:.5rem;
		margin: auto;
	}

	input{
		padding:1rem;
		width: 100%;
		text-align: center;
	}

	.md5 {
		font-weight: 300;
		opacity: 0.5;
		/* width: 100%; */
	}

	img {
		aspect-ratio: 1/1;
		height: 300px;
		width: 300px;
	}

	.get-area {
		margin-top: 3rem;
	}

	hr {
		opacity: 0.5;
		margin-bottom: 2rem;
	}	


	@media (max-width:641px) {
		.get-area{
			margin-top: 0;
		}
	}
</style>
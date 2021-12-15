<script>
	import md5 from "md5";
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
	<h1>Gavatar Look Up</h1>
	<p>Look up and get any <a href="https://en.gravatar.com/">Gavatar</a></p>
	<div class="get-area">
		<hr/>
		<input placeholder="example@example.com" type='email' on:keydown={handleEmailChange}/>
		<p class="md5">MD5 Hash: <code>{hash}</code></p>
	</div>
	<div class="avatar">
		{#if hash == ''}
			<p class="muted">Press 'enter' to get the Gavatar</p>
		{:else}
			<img src={avURL} alt={`${email}'s Gavatar Avatar.`}/>
			<br/>
			<br/>
			{#if email !== '' } [<a href={`https://www.gravatar.com/avatar/${hash}?s=2048`} target="_blank">Full Res</a>] {/if}
		{/if}
	</div>
</main>

<style>
	.muted {
		margin-top: 2rem;
		text-transform: lowercase;
		font-weight: 300;
		opacity: 0.5;
	}

	input{
		width: 60%;
		text-align: center;
	}

	.md5 {
		font-weight: 300;
		opacity: 0.3;
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
		width: 25%;
	}	

	h1 {
		color: #cc1d1d;
		text-transform: uppercase;
		font-weight: 600;
		margin-bottom: -1rem;
	}
</style>
<svelte:head>
	<title>About the battery drainer</title>
</svelte:head>

<div>
	<a href="/">Back to main page</a>

	<h1>What is the Battery Drainer ?</h1>

	<p>
		The Battery Drainer is a webpage created with the sole goal to be ecologically as inefficient as
		possible. To prove this point, I set out to make a webpage that would drain the battery of a
		device as quickly as possible.
	</p>

	<h2>Why create such a website ?</h2>

	<p>
		The idea behind the Battery Drainer was born when I tried benchmarking different websites on
		some of the most used tools for calculating C0² emissions.
	</p>
	<p>
		I quickly discovered that most of the models used as of early 2021 are completely outdated and
		ignore the consumption on the device itself, focusing instead on the DOM size (at load only), or
		number of requests. That can lead to results that make absolutely no sense, where websites that
		would run millions of javascript lines, have no SSR and plenty of repaints would score the
		highest.
	</p>

	<h2>The battery drainer to the rescue</h2>

	<p>
		With the Battery Drainer, I want to prove that these models are outdated and need to change. We
		can and we should do better than simple models based on arbitrary variables. Feel free to use it
		on ecological benchmarking tools to challenge their models and calculations.
	</p>
</div>

<style>
	div {
		color: #fff;
		max-width: 568px;
		margin: 0 auto;
	}

	a {
		color: #fff;
	}
</style>

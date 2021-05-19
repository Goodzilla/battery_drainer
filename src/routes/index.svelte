<script>
	import { onMount } from 'svelte';

	let batteryLevel = 0;

	onMount(() => {
		navigator.getBattery().then(function (battery) {
			updateLevelInfo();

			battery.addEventListener('levelchange', function () {
				updateLevelInfo();
			});

			function updateLevelInfo() {
				batteryLevel = battery.level * 100;
			}

			function drainBattery() {
				setInterval(() => {
					fibonacci(35);
				}, 50);
			}

			function fibonacci(num) {
				if (num <= 1) return 1;

				return fibonacci(num - 1) + fibonacci(num - 2);
			}

			drainBattery();
		});
	});
</script>

<svelte:head>
	<title>The Battery Drainer</title>
</svelte:head>

<div class="wrapper">
	<h1>The Battery Drainer</h1>
	<progress value={batteryLevel} max="100" />
	<p>Battery level : {batteryLevel}%</p>
	<p><a href="about">What is the Battery Drainer ?</a></p>
</div>

<style lang="scss">
	div {
		box-sizing: border-box;
		padding: 0 16px;
		max-width: 568px;
		margin: 0 auto;
	}

	h1 {
		margin-top: 24px;
		font-family: 'Courier New', Courier, monospace;
		font-weight: bold;
		font-size: 24px;
		text-align: center;
		width: 100%;
		color: #1d0d0d;
		text-shadow: 0 -1px 4px #fff, 0 -2px 10px #ff0, 0 -10px 20px #ff8000, 0 -18px 40px #f00;
	}

	p {
		width: 100%;
		color: #1d0d0d;
		margin: 8px 0;
	}

	progress[value] {
		-webkit-appearance: none;
		appearance: none;

		width: 100%;
		height: 20px;
		margin: 8px 0;
	}

	progress[value]::-webkit-progress-bar {
		background-color: #eee;
		border-radius: 2px;
		box-shadow: 0 2px 5px rgba(0, 0, 0, 0.25) inset;
	}

	progress[value]::-webkit-progress-value {
		background-image: -webkit-linear-gradient(top, rgba(255, 255, 255, 0.25), rgba(0, 0, 0, 0.25)),
			-webkit-linear-gradient(right, rgb(91, 195, 87), #f44);
		border-radius: 2px;
		background-size: 35px 20px, 100% 100%, 100% 100%;
		transition: width 2s ease;
	}

	.wrapper {
		height: 100%;
		width: 100%;
		left: 0;
		right: 0;
		top: 0;
		bottom: 0;
		position: absolute;
		background: linear-gradient(
			124deg,
			#ff2400,
			#e81d1d,
			#e8b71d,
			#e3e81d,
			#1de840,
			#1ddde8,
			#2b1de8,
			#dd00f3,
			#dd00f3
		);
		background-size: 100% 1800%;

		-webkit-animation: rainbow 18s ease infinite;
		-z-animation: rainbow 18s ease infinite;
		-o-animation: rainbow 18s ease infinite;
		animation: rainbow 18s ease infinite;
	}

	@-webkit-keyframes rainbow {
		0% {
			background-position: 0% 82%;
		}
		50% {
			background-position: 100% 19%;
		}
		100% {
			background-position: 0% 82%;
		}
	}
	@-moz-keyframes rainbow {
		0% {
			background-position: 0% 82%;
		}
		50% {
			background-position: 100% 19%;
		}
		100% {
			background-position: 0% 82%;
		}
	}
	@-o-keyframes rainbow {
		0% {
			background-position: 0% 82%;
		}
		50% {
			background-position: 100% 19%;
		}
		100% {
			background-position: 0% 82%;
		}
	}
	@keyframes rainbow {
		0% {
			background-position: 0% 82%;
		}
		50% {
			background-position: 100% 19%;
		}
		100% {
			background-position: 0% 82%;
		}
	}
</style>

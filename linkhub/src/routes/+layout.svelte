<script>
	import '../theme.postcss';
	import '@skeletonlabs/skeleton/styles/all.css';
	import '../app.postcss';
</script>

<header class="w-full top-0 bg-surface-500">
	<nav class="flex flex-row items-center w-full mx-auto justify-between">
		<div class="logo bg-primary-500 w-24 h-24 flex flex-none justify-center items-center">
			<div class="logo-text flex top-6 left-5 text-2xl leading-5 font-bold items-center">link<br>hub`</div>
			<div class="logo-plus bg-surface-500 w-14 h-14 rounded-full flex justify-center items-center absolute ml-20 mt-20">
				<div class="bg-primary-500 w-12 h-12 rounded-full flex justify-center items-center ml-1 mt-1">
					<div class="flex justify-center items-center">
						<div class="bg-white h-1 w-6 absolute rounded-full"></div>
						<div class="bg-white h-6 w-1 absolute rounded-full"></div>
					</div>
				</div>
			</div>
		</div>
		<ul class="flex flex-nowrap p-2 mr-24 items-center flex-row justify-between w-1/5 font-bold">
			<li>
				Sign Up
			</li>
			<li>
				Login
			</li>
			<li class="text-sm bg-primary-500 h-12 w-12 flex justify-center items-center rounded-full">
				ENG
			</li>
		</ul>
	</nav>
</header>

<slot />

<!-- <footer>
	bla bla bla
</footer> -->
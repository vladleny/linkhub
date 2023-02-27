<script lang="ts">
	const arr = [0];
	arr.length = 18; // Number of page__link's
	for (let index = 0; index < arr.length; index++) {
		arr[index] = index;
	}
</script>
<div class="wrapper w-full h-full bg-surface-500">
	<header class="w-full">
		<div  class="menu w-full h-24 flex justify-between items-center">
			<div class="menu__logo">
				<div class="logo__sq bg-primary-500 w-24 h-24 absolute top-0 left-0" ><div class="absolute top-6 left-5 text-2xl leading-5 font-bold">link<br>hub`</div>
					<div class="logo__round bg-surface-500 w-14 h-14 rounded-full flex justify-center items-center ml-16 mt-16">
						<div class="logo__round bg-primary-500 w-12 h-12 rounded-full flex justify-center items-center ml-1 mt-1">
							<div class="logo__plus flex justify-center items-center">
								<div class="plus__el bg-white h-1 w-6 absolute rounded-full"></div>
								<div class="plus__el bg-white h-6 w-1 absolute rounded-full"></div>
							</div>
						</div>
					</div>
				</div>
				
			</div>
			<ul class="menu__row font-bold flex mr-24 items-center">
				<li class="menu__link ">Sign Up</li>
				<li class="menu__link mx-12">Login</li>
				<li class="menu__link text-sm bg-primary-500 h-12 w-12 flex justify-center items-center rounded-full">ENG</li>
			</ul>
		</div>
	</header>
	<div class="page flex max-h-[100vh] justify-center items-center overflow-y-auto overflow-x-hidden md:mt-20 sm:mt-6">
		<div class="page__links  grid grid-cols-1  2xl:grid-cols-6 gap-8 xl:grid-cols-5 lg:grid-cols-4 md:grid-cols-4 md:gap-[50px] sm:grid-cols-2  lg:max-h-[50%] md:max-h-[100%] sm:max-h-[100%]">
			{#each arr as i }
			<div class="page__link  bg-primary-500 h-24 w-48 rounded-3xl flex justify-center items-center">
				<div class="page__link-container leading-none max-w-[200px] overflow-hidden mx-6">
					<div class="page__name  font-bold text-md">name {i + 1}</div>
					<div class="page__url font-semibold text-sm text-secondary-500 lowercase">url {i + 1}</div>
				</div>
			</div>
			{/each}
		</div>
	</div>
</div>

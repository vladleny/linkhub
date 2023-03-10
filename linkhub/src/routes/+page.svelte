<script>
	
	// @ts-nocheck
		export let showModal = false;
		
		const toggleModal = () => {
			showModal = !showModal;
		}
		
		
	
	
		let linkList = [{name: "linkhub", url: "linkhub.com", editing: false}];
		let nameInput = "";
		let urlInput = "";
	
		
	
		function addLink(){
		 const newLink = {
			  id: linkList.length + 1,
			  name: nameInput,
			  url: urlInput,
			  editing: false
		 }
		 linkList = [...linkList, newLink]; 
		 showModal = !showModal;
	}
	
		/**
		 * @param {string | number} i
		 * @param {boolean} isEditing
		 */
		function setEditing(i, isEditing){
			// @ts-ignore
			linkList[i].editing = isEditing;
		}
	
	
	
		/**
		 * @param {number} i
		 */
		function deleteLink(i){
			linkList.splice(i, 1);
			linkList = linkList;
		}
	
		
		
		
	</script>
	
	{#if showModal}
	<div class="blur absolute right-0 top-0 bg-primary-700 w-full h-full opacity-[80%] z-10"></div>
	
	<div class="add-link absolute h-full w-full right-0 top-0 flex justify-center items-center ">
		<div class="add-link__menu h-[280px] w-[280px] bg-primary-800 rounded-2xl z-10 flex items-center justify-around flex-col">
			<button on:click={toggleModal} class="pl-[200px]">X</button>
			<div class="add-link__name">
				<div class="ml-3">link-name</div>
				<input type="text" class="h-[24px] w-[180px] rounded-2xl text-black" bind:value={nameInput}>			
			</div>
			<div class="add-link__url my-[20px]">
				<div class="ml-3">link-url</div>
				<input type="text" class="h-[24px] w-[180px] rounded-2xl text-black" bind:value={urlInput}>
			</div>
			<button class="add-link__submit mb-3" on:click={addLink}>Submit</button>
		</div>
	</div>
	{/if}
	
	
	
	<div class="content w-full h-full bg-surface-500 flex justify-center items-center">
		<div class="page-links w-[1600px] h-[600px] px-12 py-16 mb-24 overflow-y-auto grid grid-cols-1  2xl:grid-cols-6 gap-4 xl:grid-cols-5 lg:grid-cols-4 md:grid-cols-4  sm:grid-cols-2  lg:max-h-[100%] md:max-h-[100%] sm:max-h-[100%]">
			{#each linkList as list, i}	
			<div class="page__link  bg-primary-500 h-24 w-48 rounded-3xl flex justify-center items-center">
					<div class="page__link-container leading-none  overflow-hidden flex flex-col items-center">
						{#if list.editing}
								<div class="blur absolute right-0 top-0 bg-primary-700 w-full h-full opacity-[80%] z-10"></div>
								<div class="add-link absolute h-full w-full right-0 top-0 flex justify-center items-center ">
									<div class="add-link__menu h-[280px] w-[280px] bg-primary-800 rounded-2xl z-10 flex items-center justify-center flex-col">
										<div class="add-link__name">
											<input type="text" class="h-[24px] w-[180px] rounded-2xl my-6 text-black" bind:value={list.name}>			
										</div>
										<div class="add-link__url my-[20px]">
											<input type="text" class="h-[24px] w-[180px] rounded-2xl my-6 text-black" bind:value={list.url}>
										</div>
										<button class="add-link__submit" on:click={() => setEditing(i, false)}>Submit</button>
									</div>
								</div>
						{:else}
						<div class="page__buttons flex justify-end w-[150px]">
							<button class="z-0" on:click={() => setEditing(i, true)}>ch</button>
							<div class="mx-1"></div>
							<button class="z-0" on:click={() => deleteLink(i)}>x</button>
						</div>
						<div class="my-0.5 "></div>
						<div class="page__info mx-8 mb-2 pb-2 flex flex-col overflow-hidden whitespace-nowrap max-w-[150px]">
							<div class="page__name font-bold text-md ">{list.name}</div>
							<div class="page__url font-semibold text-sm text-secondary-500 lowercase">{list.url}</div>
						</div>
						
						{/if}
	
						
						
					</div>
				</div>
				{/each}
		</div>
	</div>
	


<!-- <div class="wrapper w-full h-full bg-surface-500">
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
</div> -->

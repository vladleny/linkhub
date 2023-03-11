<script>

	
	import '../theme.postcss';
	import '@skeletonlabs/skeleton/styles/all.css';
	import '../app.postcss';

	import Modal from './+page.svelte'
	
	let showModal = false;
	
	
	

</script>




<Modal {showModal}></Modal>


<slot />




<!-- <footer>
	bla bla bla
</footer> -->
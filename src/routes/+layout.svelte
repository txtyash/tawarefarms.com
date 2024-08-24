<script lang="ts">
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<div class="flex items-center">
					<img src="/images/logo.svg" alt="Grape icon" class="w-8 h-8 mr-2" />
					<span class="text-xl lg:text-4xl logo-font">TF</span>
				</div>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a class="btn btn-sm variant-ghost-surface" href="#"> Home </a>
				<a class="btn btn-sm variant-ghost-surface" href="#about-us"> About </a>
				<a class="btn btn-sm variant-ghost-surface" href="#contact-us"> Contact </a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>

<style>
</style>

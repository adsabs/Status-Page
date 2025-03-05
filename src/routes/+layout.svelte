<script lang="ts">
	import '../app.css';
</script>

<slot />
<footer class="footer footer-center bg-base-300 text-base-content p-4 sticky top-[100vh]">
	<aside>
		<p>
			<a href="https://ui.adsabs.harvard.edu">Astrophysics Data System</a> |
			<a href="https://scixplorer.org">Science Explorer</a>
		</p>
	</aside>
</footer>

<style lang="postcss">
	a {
		@apply text-blue-500 link;
	}
</style>

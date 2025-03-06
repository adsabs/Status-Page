<script lang="ts">
	import '../app.css';
</script>

<slot />
<footer class="footer bg-black text-white p-4 sticky top-[100vh]">
	<div class="flex max-w-3xl min-w-[50vw] mx-auto justify-evenly">
		<div class="max-w-80">
			&copy; The SAO Astrophysics Data System
			<div class="my-5">
				<p>
					<i class="fa fa-envelope" aria-hidden="true"></i>
					adshelp[at]cfa.harvard.edu
				</p>
				<p>
					The ADS is operated by the Smithsonian Astrophysical Observatory under NASA Cooperative
					Agreement <em>80NSSC21M0056</em>
				</p>
			</div>
			<div class="flex flex-row my-5">
				<div class="mx-4">
					<a href="http://www.si.edu" target="_blank" rel="noreferrer noopener">
						<img
							id="smithsonian-logo"
							src="https://ui.adsabs.harvard.edu/styles/img/smithsonian-logo.svg"
							alt="Smithsonian logo"
							width="70px"
						/>
					</a>
				</div>
				<div class="mx-4">
					<a href="https://www.cfa.harvard.edu/" target="_blank" rel="noreferrer noopener">
						<img
							src="https://ui.adsabs.harvard.edu/styles/img/cfa.png"
							alt="Harvard Center for Astrophysics logo"
							id="cfa-logo"
							width="120px"
						/>
					</a>
				</div>
				<div class="mx-4">
					<a href="http://www.nasa.gov" target="_blank" rel="noreferrer noopener">
						<img
							src="https://ui.adsabs.harvard.edu/styles/img/nasa-partner.svg"
							alt="NASA logo"
							id="nasa-logo"
							width="70px"
						/>
					</a>
				</div>
			</div>
			<div>
				*The material contained in this document is based upon work supported by a National
				Aeronautics and Space Administration (NASA) grant or cooperative agreement. Any opinions,
				findings, conclusions or recommendations expressed in this material are those of the author
				and do not necessarily reflect the views of NASA.
			</div>
		</div>
		<div>
			<div>Resources</div>
			<ul>
				<li>
					<a href="https://ui.adsabs.harvard.edu/about/" target="_blank" rel="noreferrer noopener">
						<i class="fa fa-question-circle" aria-hidden="true"></i> About ADS
					</a>
				</li>
				<li>
					<a href="https://ui.adsabs.harvard.edu/help/" target="_blank" rel="noreferrer noopener">
						<i class="fa fa-info-circle" aria-hidden="true"></i> ADS Help
					</a>
				</li>
				<li>
					<a
						href="https://ui.adsabs.harvard.edu/help/whats_new/"
						target="_blank"
						rel="noreferrer noopener"
					>
						<i class="fa fa-bullhorn" aria-hidden="true"></i> What's New
					</a>
				</li>
				<li>
					<a
						href="https://ui.adsabs.harvard.edu/about/careers/"
						target="_blank"
						rel="noreferrer noopener"
					>
						<i class="fa fa-group" aria-hidden="true"></i> Careers@ADS
					</a>
				</li>
				<li>
					<a
						href="https://ui.adsabs.harvard.edu/help/accessibility/"
						target="_blank"
						rel="noreferrer noopener"
					>
						<i class="fa fa-universal-access" aria-hidden="true"></i>
						Web Accessibility Policy
					</a>
				</li>
			</ul>
		</div>
		<div>
			<div>Social</div>
			<ul>
				<li>
					<a href="https://twitter.com/adsabs" target="_blank" rel="noreferrer noopener">
						<i class="fa fa-twitter" aria-hidden="true"></i> @adsabs
					</a>
				</li>
				<li>
					<a href="https://ui.adsabs.harvard.edu/blog/" target="_blank" rel="noreferrer noopener">
						<i class="fa fa-newspaper-o" aria-hidden="true"></i> ADS Blog
					</a>
				</li>
			</ul>
		</div>
		<div>
			<div>Project</div>
			<ul>
				<li>
					<a
						href="https://ui.adsabs.harvard.edu/help/privacy/"
						target="_blank"
						rel="noreferrer noopener">Privacy Policy</a
					>
				</li>
				<li>
					<a
						href="https://ui.adsabs.harvard.edu/help/terms"
						target="_blank"
						rel="noreferrer noopener">Terms of Use</a
					>
				</li>
				<li>
					<a href="https://www.cfa.harvard.edu/sao" target="_blank" rel="noreferrer noopener"
						>Smithsonian Astrophysical Observatory</a
					>
				</li>
				<li>
					<a href="https://www.si.edu" target="_blank" rel="noreferrer noopener"
						>Smithsonian Institution</a
					>
				</li>
				<li>
					<a href="https://www.nasa.gov" target="_blank" rel="noreferrer noopener">NASA</a>
				</li>
			</ul>
		</div>
	</div>
</footer>

<style lang="postcss">
	a {
		@apply text-blue-500 link;
	}
</style>

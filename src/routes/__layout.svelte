<script lang="ts">
	let lightTheme =
		typeof window === 'undefined' || window.matchMedia('(prefers-color-scheme: light)').matches;
	function switchTheme() {
		lightTheme = !lightTheme;
		let themeLink = document.head.querySelector<HTMLLinkElement>('#theme');
		if (!themeLink) {
			themeLink = document.createElement('link');
			themeLink.rel = 'stylesheet';
			themeLink.id = 'theme';
		}
		themeLink.href = `/smui${lightTheme ? '' : '-dark'}.css`;
		document.head
			.querySelector<HTMLLinkElement>('link[href$="/smui-dark.css"]')
			?.insertAdjacentElement('afterend', themeLink);
	}
</script>

<header>
	<div class="mdc-top-app-bar mdc-top-app-bar__row">
		<div class="mdc-top-app-bar__row">
			<section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start">
				<button
					class="material-icons mdc-top-app-bar__navigation-icon mdc-icon-button"
					aria-label="Close">
					<img src="src/routes/Beigua2024g.png" alt="Logo Beigua2025">
				</button>
				
				<a href="/home.svelte" class="mdc-top-app-bar__title">Homepage</a>
			</section>
			<section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-end">
				<button
					on:click={switchTheme}
					class="material-icons mdc-top-app-bar__navigation-icon mdc-icon-button"
					aria-label="Brightness6Icon"
				>
					brightness_6
				</button>
			</section>
		</div>
	</div>
</header>

<section class=" ">
	<div>
	<div class="my-card-section">
		<div class="mdc-card my-card-center my-card-wrapper">
			<div
				class="mdc-card__media mdc-card__media--16-9"
				style="background-image: url('src/routes/articolo1.jpeg')"
			/>
			<div class="my-card-wrapper">
				<div class="mdc-typography--headline6">Ucraina</div>
				<div class="mdc-typography--body2">Esplosa</div>
			</div>
		</div>

			<div class="mdc-card my-card-center my-card-wrapper">
				<div
					class="mdc-card__media mdc-card__media--16-9"
					style="background-image: url('src/routes/articolo2.jpeg')"
				/>
				<div class="my-card-wrapper">
					<div class="mdc-typography--headline6">Volpi</div>
					<div class="mdc-typography--body2">Bellissime!</div>
				</div>
			</div>

			<div class="mdc-card my-card-center my-card-wrapper">
				<div
					class="mdc-card__media mdc-card__media--16-9"
					style="background-image: url('src/routes/articolo3.jpeg')"
				/>
				<div class="my-card-wrapper">
					<div class="mdc-typography--headline6">Siriane</div>
					<div class="mdc-typography--body2">Così così</div>
				</div>
			</div>
	</div>
</div>
</section>

<footer class="footer">
	<div class="mdc-top-app-bar mdc-top-app-bar__row">
		<div class="mdc-top-app-bar__row">
			<section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-end">
				<button
					class="material-icons mdc-top-app-bar__navigation-icon mdc-icon-button my-card-icon"
					aria-label="Insta">
					<img src="src/routes/LogoInsta.png" alt="Logo Instagram">
				</button>
			</section>
		</div>
	</div>
</footer>

<style>
	.my-card-center {
		width: 450px;
	}
	.my-card-wrapper {
		margin: 16px;
	}
	.my-card-icon
	{
		width: 64px;
	}
	.my-card-section {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;
	}
	.mdc-top-app-bar,
	.mdc-top-app-bar__title,
	.mdc-top-app-bar__navigation-icon {
		background-color: var(--mdc-theme-surface) !important;
		color: var(--mdc-theme-on-primary) !important;
	}
	.mdc-typography--body2 {
		opacity: 0.6;
	}
	.footer {
		overflow: hidden;
		position: fixed;
		width: 100%;
		bottom: 0;
		background-color: #418354 !important;
		color: white !important;
	}
	header
	{
		border-bottom: 1px solid rgb(209, 209, 209);
	}
</style>

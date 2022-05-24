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
					aria-label="Close"
				>
					home
				</button>
				<a href="/home.svelte" class="mdc-top-app-bar__title">Homepage</a>
			</section>
			<section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-end">
				<a href="/home.svelte" class="mdc-top-app-bar__title">Articoli</a>
				<a href="/home.svelte" class="mdc-top-app-bar__title">Progetto</a>
				<a href="/home.svelte" class="mdc-top-app-bar__title">Chi Siamo</a>
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

<section class="my-card-cards ">
	<div>
		<div class="my-card-section">
			<div class="mdc-card my-card-side my-card-wrapper">
				<div
					class="mdc-card__media mdc-card__media--16-9"
					style="background-image: url('src/routes/articolo1.jpeg')"
				/>
			</div>

			<div class="mdc-card my-card-center my-card-wrapper">
				<div
					class="mdc-card__media mdc-card__media--16-9"
					style="background-image: url('src/routes/articolo2.jpeg')"
				/>
				<div class="my-card-wrapper">
					<div class="mdc-typography--headline6">Volpiiiiiiii</div>
					<div class="mdc-typography--body2">Drindindindindindindin</div>
				</div>
			</div>

			<div class="mdc-card my-card-side my-card-wrapper">
				<div
					class="mdc-card__media mdc-card__media--16-9"
					style="background-image: url('src/routes/articolo3.jpeg')"
				/>
			</div>
		</div>
	</div>
</section>

<footer class="footer">
	<div class="mdc-top-app-bar mdc-top-app-bar--prominent ">
		<section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start mdc-card__action-buttons">
			<img src="src/routes/Beigua2024.png" alt="beigua logo" style="width:86px;" />
		</section>
	</div>
	<div class="mdc-top-app-bar--prominent-fixed-adjust ">
	</div>
</footer>

<style>
	.my-card-cards {
		padding-top: 64px;
	}
	.my-card-center {
		width: 600px;
	}
	.my-card-side {
		width: 300px;
		opacity: 0.7;
	}
	.my-card-wrapper {
		margin: 16px;
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
</style>

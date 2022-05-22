<script lang="ts">
	let lightTheme = typeof window === 'undefined' || window.matchMedia('(prefers-color-scheme: light)').matches;
	function switchTheme() 
	{
		lightTheme = !lightTheme;
		let themeLink = document.head.querySelector<HTMLLinkElement>('#theme');
		if (!themeLink) 
		{
			themeLink = document.createElement('link');
			themeLink.rel = 'stylesheet';
			themeLink.id = 'theme';
		}
		themeLink.href = `/smui${lightTheme ? '' : '-dark'}.css`;
		document.head .querySelector<HTMLLinkElement>('link[href$="/smui-dark.css"]') ?.insertAdjacentElement('afterend', themeLink);
	}
</script>

<header class="mdc-top-app-bar">
	<div class="mdc-top-app-bar__row">
		<section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start">
			<button class="material-icons mdc-top-app-bar__navigation-icon mdc-icon-button" aria-label="Close">menu</button>
			<a href="/home.svelte" class="mdc-top-app-bar__title">Beigua 2024</a>
		</section>
		<section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-end" role="toolbar">
			<a href="/home.svelte" class="mdc-top-app-bar__title">Articoli</a>
			<a href="/home.svelte" class="mdc-top-app-bar__title">Progetto</a>
			<a href="/home.svelte" class="mdc-top-app-bar__title">Chi Siamo</a>
			<button on:click={switchTheme} class="material-icons mdc-top-app-bar__action-item mdc-icon-button" aria-label="Brightness6Icon">brightness_6</button>
		</section>
	</div>
</header>

<div style="margin: 80px;"><p>cacaaaaa</p></div>

<div class="mdc-card my-card">
	<div class="mdc-card__primary-action">
	  <div class="mdc-card__media mdc-card__media--square my-card__media">
		<div class="mdc-card__media-content">Title</div>
	  </div>
	  <!-- ... additional primary action content ... -->
	  <div class="mdc-card__ripple"></div>
	</div>
	<div class="mdc-card__actions">
	  <div class="mdc-card__action-buttons">
		<button class="mdc-button mdc-card__action mdc-card__action--button">
		  <div class="mdc-button__ripple"></div>
		  <span class="mdc-button__label">Monte Tarineperepepepepepe</span>
		</button>
	  </div>
	</div>
  </div>

<style>
.my-card
{
  height: 350px;
  width: 350px;
}
.my-card__media 
{
  background-image: url("src/routes/Tarine.jpg");
}
</style>





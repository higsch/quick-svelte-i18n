<script>
  import translations from './translations';

  import { dict, locale, t } from './i18n';

  $: languages = Object.keys(translations);

  $: dict.set(translations);
</script>

<main>
  <select bind:value={$locale}>
    {#each languages as lang}
      <option value={lang}>
        {lang}
      </option>
    {/each}
  </select>
  <h1>{$t('title.helloworld')}</h1>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

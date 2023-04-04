<script lang="ts">
	const apikey = 'xxxx';

	function doCompletion() {
		const body = {
			prompt:
				'Negate the following sentence.The price for bubblegum increased on thursday.\n\n Negated Sentence:',
			max_tokens: 50
		};

		fetch(
			'https://sandboxapisystem.azure-api.net/openai/deployments/text-davinci-003/completions?api-version=2022-12-01',
			{
				method: 'POST',
				body: JSON.stringify(body),
				// Request headers
				headers: {
					'Content-Type': 'application/json',
					'Cache-Control': 'no-cache',
					'api-key': apikey
				}
			}
		)
			.then((response) => {
				console.log(response.status);
				console.log(response.text());
			})
			.catch((err) => console.error(err));
	}
</script>

<ion-card>
	<ion-card-header>
		<ion-card-subtitle>Great success!!</ion-card-subtitle>
		<ion-card-title>Welcome to your app!</ion-card-title>
	</ion-card-header>

	<ion-card-content>
		Thank you for using this starter. Click buttons below to open these guides (will open in new
		window). Don't forget to open DevTools to see this app in mobile mode. Happy coding!!!
	</ion-card-content>

	<ion-item>
		<ion-label>Open completion</ion-label>
		<ion-button on:click={doCompletion} fill="outline" slot="end">doCompletion</ion-button>
	</ion-item>
</ion-card>

<script lang="ts">
	const flagMappings = {
		A: 'flags/A.png',
		B: 'flags/B.png',
		C: 'flags/C.png',
		D: 'flags/D.png',
		E: 'flags/E.png',
		F: 'flags/F.png',
		G: 'flags/G.png',
		H: 'flags/H.png',
		I: 'flags/I.png',
		J: 'flags/J.png',
		K: 'flags/K.png',
		L: 'flags/L.png',
		M: 'flags/M.png',
		N: 'flags/N.png',
		O: 'flags/O.png',
		P: 'flags/P.png',
		Q: 'flags/Q.png',
		R: 'flags/R.png',
		S: 'flags/S.png',
		T: 'flags/T.png',
		U: 'flags/U.png',
		V: 'flags/V.png',
		W: 'flags/W.png',
		X: 'flags/X.png',
		Y: 'flags/Y.png',
		Z: 'flags/Z.png'
	};

	let boom = 'Ahoy there matey';

	function makeFlagSrcArray(word: string) {
		const srcArray = [];
		for (let i = 0; i < word.length; i++) {
			const letter = word[i];
			if (letter === ' ') {
				srcArray.push('br');
			} else {
				srcArray.push(flagMappings[letter.toUpperCase()]);
			}
		}
		return srcArray;
	}

	$: flagSrc = makeFlagSrcArray(boom);
</script>

<input bind:value={boom} />

<div class="flags">
	{#each flagSrc as src}
		{#if src == 'br'}
			<br />
		{:else}
			<img {src} alt={src} />
		{/if}
	{/each}
</div>

<style>
	input {
		margin-bottom: 24px;
	}
	img {
		width: 100px;
	}
	@media only screen and (max-width: 600px) {
		img {
			width: 40px;
		}
	}
	img + img {
		margin-left: 12px;
	}
</style>

<script>
	import './Progressbar.css';

	export let height = '10px';

	export /**
	 * @type {any}
	 */ let backgroundColor = '#f5f5f5';

	export /**
	 * @type {any}
	 */ let color = '#5681d3';

	export let progress = 0;

	export let active = false;

	export let indeterminate = false;
	export let showPercent = true;

	let bgstyle = backgroundColor ? `background-color: ${backgroundColor}` : '';
	let style = color ? `background-color: ${color}` : '';
	style += ';height:' + height;

	$: {
		if (indeterminate) {
		}
	}

	$: {
		if (progress >= 0 && progress <= 100) {
			style += ';' + 'width:' + (indeterminate ? 0 : progress) + '%;';
		} else {
			progress = 100;
		}
	}
</script>

<div class="progressbar-holder">
	<div class="progressbar-segments">
		<div class="progressbar-innersegment">
			<div class="progressbar-outer" style={bgstyle}>
				<div
					class="progressbar-inner {active && !indeterminate ? 'active' : ''} {indeterminate
						? 'indeterminate'
						: ''}"
					{style}
				/>
			</div>
		</div>
		{#if showPercent}
			<span class="progressbar-text">
				{progress}%
			</span>
		{/if}
	</div>
</div>
 
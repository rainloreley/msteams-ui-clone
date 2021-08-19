<script>
	import MenuDots from '../components/MenuDots.svelte';
	import md5 from 'md5';

	export let name;
	export let channels;
	export let channelsvisible;

	function toggleChannelVisibility() {
		channelsvisible = !channelsvisible;
	}
</script>

<li>
	<teaminfo on:click={() => toggleChannelVisibility()}>
		<svg
			viewBox="-10 -10 32 32"
			class="app-svg icons-triangle-down-small {channelsvisible
				? 'triangle-expanded'
				: ''}"
			><path
				class="icons-default-fill"
				d="M3.07615 4.61732C3.23093 4.24364 3.59557 4 4.00003 4H8.00003C8.40449 4 8.76913 4.24364 8.92391 4.61732C9.07869 4.99099 8.99313 5.42111 8.70714 5.70711L6.70714 7.70711C6.31661 8.09763 5.68345 8.09763 5.29292 7.70711L3.29292 5.70711C3.00692 5.42111 2.92137 4.99099 3.07615 4.61732Z"
			/></svg
		>
		<teamimagewrapper>
			<img
				src="https://source.boringavatars.com/marble/100/{md5(
					name
				)}?colors=92A1C6,146A7C,F0AB3D,C271B4,C20D90"
				alt="team"
			/>
		</teamimagewrapper>
		<p>{name}</p>
		<svg
			viewBox="-6 -6 32 32"
			class="menudots"
			focusable="false"
			role="presentation"><MenuDots /></svg
		>
	</teaminfo>
	{#if channelsvisible}
		<ul class="teamchannels">
			{#each channels as item}
				<li class="channelitem {item.selected ? 'channelselected' : ''}">
					<p>{item.name}</p>
					<svg
						viewBox="-6 -6 32 32"
						class="menudots"
						focusable="false"
						role="presentation"><MenuDots /></svg
					>
				</li>
			{/each}
		</ul>
	{/if}
</li>

<style>
	.teamchannels {
		display: block;
		width: 100%;
		list-style: none;
		margin: 0;
		padding: 0;
	}
	li {
		padding-top: 8px;
		width: 100%;
	}

	li teaminfo {
		display: flex;
	}

	teaminfo:hover {
		background-color: #fafafa;
	}

	li teaminfo * {
		align-self: center;
	}

	teaminfo p {
		margin-left: 16px;
		font-size: 14px;
		color: #616161;
	}

	teaminfo .menudots {
		width: 30px;
		height: 30px;
		fill: #616161;
		position: absolute;
		right: 8px;
	}

	teamimagewrapper {
		overflow: hidden;
		width: 30px;
		height: 30px;
		border-radius: 5px;
	}

	teamimagewrapper img {
		scale: 200%;
	}

	svg.icons-triangle-down-small {
		width: 30px;
		fill: black;
		transform: rotate(-90deg);
	}

	svg.triangle-expanded {
		fill: gray !important;
		transform: rotate(0deg);
	}

	.channelitem:hover {
		background-color: #fafafa;
	}

	.channelselected {
		background-color: #ffffff;
	}

	.channelitem {
		display: flex;
		padding-top: 0 !important;
	}

	.channelitem:hover svg {
		display: block;
	}

	.channelitem * {
		align-self: center;
	}

	.channelitem p {
		color: #616161;
		margin: 8px;
		margin-left: calc(16px + 30px + 30px);
		font-size: 14px;
	}

	.channelitem svg {
		width: 30px;
		height: 30px;
		fill: #616161;
		position: absolute;
		right: 8px;
		display: none;
	}

	@media (prefers-color-scheme: dark) {
		teaminfo p {
			color: #adadad;
		}

		teaminfo .menudots {
			fill: #adadad;
		}

		svg.icons-triangle-down-small {
			fill: #adadad;
		}

		.channelitem p {
			color: #adadad;
		}

		.channelitem:hover {
			background-color: #252525;
		}

		.channelselected {
			background-color: #2a2a2a;
		}

		.channelitem svg {
			fill: #adadad;
		}

		teaminfo:hover {
			background-color: #252525;
		}
	}
</style>

<script>
	import MSTHeader from './MSTHeader.svelte';
	import MSTSidebar from './MSTSidebar.svelte';
	import MSTTeamSelection from './teamstab/MSTTeamSelection.svelte';
	import MSTTeamChat from './teamstab/MSTTeamChat.svelte';
	import msteamsdataset from './data/msteamsdataset.json';

	let selectedChannel = {
		team: msteamsdataset.teams.find(
			(e) => e.id == 'b6af7869-52c6-4b87-bd83-c627e911e43d'
		),
		channel: msteamsdataset.teams
			.find((e) => e.id == 'b6af7869-52c6-4b87-bd83-c627e911e43d')
			.channels.find((e) => e.id == 'a09b084a-2724-4c18-91a0-883ed0be7c39'),
	};

	function loadChannel(team, channel) {
		selectedChannel = {
			team: team,
			channel: channel,
		};
	}
</script>

<main>
	<MSTHeader />
	<columnview>
		<MSTSidebar />
		<MSTTeamSelection teamchannelselectionhandler={loadChannel} />
		<MSTTeamChat channeldata={selectedChannel} />
	</columnview>
</main>

<style>
	:root {
		--ms-brandbg1: #e9eaf6;
		--ms-brandborder1: #b2b5ff;

		--ms-brandfg1: #494b83;
		--ms-brandbg2: #3d3e66;
		--ms-chatbg: #f5f5f5;
		--ms-teamslistbg: #f0f0f0;
		--ms-sidebarbg: #ebebeb;
		--ms-searchbarbg: #dddde5;
		--mspurple: #6264a7;
		--mspurpledarkmode: #9ea2ff;
	}

	:global(body) {
		padding: 0;
		background-color: rgb(250, 249, 248);
		position: fixed;
		scrollbar-width: none;
	}
	:global(body::-webkit-scrollbar) {
		width: 0;
		height: 0;
		display: none;
	}

	main {
		width: 100%;
		height: 100%;
		margin: 0 auto;
	}
	columnview {
		display: flex;
		flex-direction: row;
		height: calc(100% - 48px);
		background-color: red;
	}

	:global(.app-trailing-shadow) {
		position: relative;
	}

	:global(.app-trailing-shadow::before) {
		background: linear-gradient(to right, transparent, #aaa);
		content: '';
		height: 100%;
		opacity: 0.2;
		pointer-events: none;
		position: absolute;
		right: 0;
		width: 0.8rem;
		z-index: 2;
	}

	@media (prefers-color-scheme: dark) {
		:global(.app-trailing-shadow::before) {
			background: linear-gradient(to right, transparent, #000);
		}
	}
</style>

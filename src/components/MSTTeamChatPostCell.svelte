<script>
	import ProfilePictureWithStatus from './ProfilePictureWithStatus.svelte';
	import moment from 'moment';

	export let user;
	export let message;
</script>

<postcell>
	<profilepicture>
		<ProfilePictureWithStatus
			image={user.pfp}
			bgcolor={'#f5f5f5'}
			bgcolordark={'#202020'}
			size={40}
			status={user.status}
		/>
	</profilepicture>

	<postframe>
		<originalmessage class={message.postedbyme ? 'postedbyme' : ''}>
			<ogmcontent>
				<header>
					<p class="sendername">{user.name}</p>
					<p class="timestamp">
						{moment(message.timestamp * 1000).format('YYYY') ==
						moment().format('YYYY')
							? moment(message.timestamp * 1000).format('DD.MM. HH:mm')
							: moment(message.timestamp * 1000).format('DD.MM.YY HH:mm')}
					</p>
				</header>
				{#if typeof message.title === 'string'}
					<p class="messagetitle">{message.title}</p>{/if}
				<p class="messagecontent">{@html message.message}</p>
			</ogmcontent>
		</originalmessage>
		<replysection>
			{#each message.replies as reply}
				<reply
					style={reply.postedbyme
						? 'border-left: 3px solid var(--mspurple);'
						: ''}
				>
					<ProfilePictureWithStatus
						image={reply.user.pfp}
						size={32}
						bgcolor={'#fafafa'}
						bgcolordark={'#252525'}
						status={reply.user.status}
					/>
					<replycontent>
						<header>
							<p class="sendername">{reply.user.name}</p>
							<p class="timestamp">
								{moment(reply.timestamp * 1000).format('YYYY') ==
								moment().format('YYYY')
									? moment(reply.timestamp * 1000).format('DD.MM. HH:mm')
									: moment(reply.timestamp * 1000).format('DD.MM.YY HH:mm')}
							</p>
						</header>
						<p class="messagecontent">{@html reply.message}</p>
					</replycontent>
				</reply>
			{/each}
			<replybutton>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					width="24"
					height="24"
					viewBox="0 0 24 24"
					fill="none"
					stroke="#616161"
					stroke-width="2"
					stroke-linecap="round"
					stroke-linejoin="round"
					class="feather feather-corner-down-left"
					><polyline points="9 10 4 15 9 20" /><path
						d="M20 4v7a4 4 0 0 1-4 4H4"
					/></svg
				>
				<p>Reply</p>
			</replybutton>
		</replysection>
	</postframe>
</postcell>

<style>
	postcell {
		width: 100%;
		display: flex;
		margin-top: 32px;
	}

	postcell profilepicture {
		margin-top: 8px;
	}

	postframe {
		width: calc(100% - 40px - 8px);
		background-color: transparent;
		display: flex;
		flex-direction: column;
	}

	/*originalmessage::before {
		content: '';
		pointer-events: none;
		height: 100%;
		background: var(--mspurple);
		width: 0.3rem;
		position: absolute;
		top: 0;
		z-index: 3;
		left: auto;
	}*/

	/*padding-top: 12px;
		padding-left: 16px;
		padding-right: 16px;*/

	originalmessage {
		display: block;
		width: 100%;
		background-color: white;
		border-radius: 4px 4px 0px 0px;
		box-shadow: 0 0.2rem 0.4rem -0.075rem rgba(0, 0, 0, 0.1);
	}

	originalmessage.postedbyme {
		border-left: 3px solid var(--mspurple);
		width: calc(100% - 3px);
	}

	ogmcontent {
		display: block;
		margin-top: 12px;
		margin-left: 16px;
		margin-right: 16px;
		margin-bottom: 12px;
	}

	ogmcontent header {
		display: flex;
	}

	ogmcontent header * {
		align-self: center;
	}

	ogmcontent header p.timestamp {
		color: #777;
		font-size: 12px;
		margin-left: 8px;
		margin-block-start: 0;
		margin-block-end: 0;
	}

	ogmcontent header p.sendername {
		font-weight: 600;
		font-size: 12px;
		color: #242424;
		margin-block-start: 0;
		margin-block-end: 0;
	}

	.messagetitle {
		font-size: 20px;
		font-weight: 600;
		margin-block-start: 0;
		margin-block-end: 0;
		margin-top: 4px;
	}

	.messagecontent {
		margin-block-start: 0;
		margin-block-end: 0;
		color: #242424;
		font-size: 14px;
		line-height: 1.4286;
	}

	replysection {
		background-color: #fafafa;
		display: block;
		width: 100%;
		/*height: 30px;*/
		border-radius: 0px 0px 4px 4px;
		box-shadow: 0 0.2rem 0.4rem -0.075rem rgba(0, 0, 0, 0.1);
	}

	replybutton {
		margin-top: 4px;
		margin-bottom: 2px;
		display: flex;
	}

	replybutton * {
		align-self: center;
	}

	replybutton svg {
		width: 16px;
		margin-left: 16px;
	}

	replybutton p {
		color: #777;
		margin-left: 8px;
		font-size: 12px;
		margin-block-start: 0;
		margin-block-end: 0;
	}

	reply {
		display: flex;
		padding-top: 8px;
		padding-bottom: 8px;
	}

	replycontent {
		margin-top: 2px;
		margin-left: 4px;
		margin-right: 8px;
	}

	replycontent header {
		display: flex;
	}

	replycontent header * {
		align-self: center;
	}

	replycontent header p.timestamp {
		color: #777;
		font-size: 12px;
		margin-left: 8px;
		margin-block-start: 0;
		margin-block-end: 0;
	}

	replycontent header p.sendername {
		font-weight: 600;
		font-size: 12px;
		color: #242424;
		margin-block-start: 0;
		margin-block-end: 0;
	}

	@media (prefers-color-scheme: dark) {
		originalmessage {
			background-color: #2a2a2a;
			box-shadow: 0 0.2rem 0.4rem -0.075rem rgba(0, 0, 0, 0.6);
		}

		ogmcontent header p.timestamp {
			color: #999;
		}

		ogmcontent header p.sendername {
			color: white;
		}

		.messagetitle {
			color: white;
		}

		.messagecontent {
			color: #ddd;
		}

		replysection {
			background-color: #252525;
			box-shadow: 0 0.2rem 0.4rem -0.075rem rgba(0, 0, 0, 0.6);
		}

		replybutton p {
			color: #d6d6d6;
		}

		replybutton svg {
			stroke: #d6d6d6;
		}

		replycontent header p.timestamp {
			color: #999;
		}

		replycontent header p.sendername {
			color: white;
		}

		/*background-color: var(--mspurpledarkmode);*/
	}
</style>

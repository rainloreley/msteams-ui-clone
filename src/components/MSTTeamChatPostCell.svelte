<script>
	import ProfilePictureWithStatus from './ProfilePictureWithStatus.svelte';
	import moment from 'moment';
	import { onMount } from 'svelte';

	export let message;

	let repliesExpanded = false;

	let replyUsers = '';

	onMount(async () => {
		buildReplyUsers();
	});

	function buildReplyUsers() {
		var users = [];
		for (var i = 0; i < message.replies.length; i++) {
			if (users.findIndex((e) => e.id === message.replies[i].user.id) === -1) {
				users.push({
					id: message.replies[i].user.id,
					firstname: message.replies[i].user.firstname,
					lastname: message.replies[i].user.lastname,
				});
			}
		}

		var usersentence = '';

		for (var i = 0; i < users.length; i++) {
			if (i === users.length - 1) {
				// last person, add "and" if necessary
				if (usersentence !== '') {
					usersentence = `${usersentence} and ${users[i].firstname}`;
				} else {
					usersentence = users[i].firstname;
				}
			} else {
				usersentence = `${usersentence}${i !== 0 ? ', ' : ''}${
					users[i].firstname
				}`;
			}
		}

		replyUsers = usersentence;
		console.log(replyUsers);
	}
</script>

<postcell>
	<profilepicture>
		<ProfilePictureWithStatus
			image={message.user.pfp}
			bgcolor={'#f5f5f5'}
			bgcolordark={'#202020'}
			size={40}
			status={message.user.status}
		/>
	</profilepicture>

	<postframe>
		<originalmessage class={message.postedbyme ? 'postedbyme' : ''}>
			<ogmcontent>
				<header>
					<p class="sendername">
						{message.user.firstname ?? ''}
						{message.user.lastname ?? ''}
					</p>
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
			{#if message.mentionschannel}
				<mentionchannelicon>
					<svg
						viewBox="-6 -6 32 32"
						class="app-svg icons-teams app-bar-icons-fill-colors"
						focusable="false"
						role="presentation"
						><path
							class="icons-default-fill icons-filled"
							d="M12.4755 8.01419C12.9883 8.01419 13.411 8.40023 13.4687 8.89757L13.4755 9.01419V13.3816C13.4755 15.3059 11.9155 16.8658 9.99118 16.8658C8.131 16.8658 6.61129 15.4081 6.51205 13.5727L6.50689 13.3816V9.01419C6.50689 8.50135 6.89293 8.07868 7.39027 8.02092L7.50689 8.01419H12.4755ZM5.7748 8.01359C5.63281 8.25885 5.54142 8.53706 5.5149 8.83394L5.50689 9.01419V13.3816L5.51177 13.5926C5.54156 14.2354 5.70666 14.8428 5.97923 15.387C5.6396 15.5306 5.26595 15.6096 4.87385 15.6096C3.35271 15.6096 2.1093 14.4205 2.02243 12.9211L2.01758 12.7533V9.01419C2.01758 8.50135 2.40362 8.07868 2.90096 8.02092L3.01758 8.01419L5.7748 8.01359ZM14.2076 8.01359L16.9919 8.01419C17.5047 8.01419 17.9274 8.40023 17.9852 8.89757L17.9919 9.01419V12.7541C17.9919 14.3311 16.7135 15.6096 15.1364 15.6096C14.7355 15.6096 14.3539 15.527 14.0077 15.3778C14.2698 14.8512 14.4314 14.2666 14.4676 13.6485L14.4755 13.3816V9.01419L14.47 8.86493C14.4472 8.55642 14.3545 8.26737 14.2076 8.01359ZM9.98931 2.98914C11.2194 2.98914 12.2167 3.98636 12.2167 5.2165C12.2167 6.44664 11.2194 7.44386 9.98931 7.44386C8.75917 7.44386 7.76194 6.44664 7.76194 5.2165C7.76194 3.98636 8.75917 2.98914 9.98931 2.98914ZM14.9765 3.61727C16.0332 3.61727 16.8898 4.47388 16.8898 5.53056C16.8898 6.58725 16.0332 7.44386 14.9765 7.44386C13.9198 7.44386 13.0632 6.58725 13.0632 5.53056C13.0632 4.47388 13.9198 3.61727 14.9765 3.61727ZM5.0179 3.61727C6.07459 3.61727 6.9312 4.47388 6.9312 5.53056C6.9312 6.58725 6.07459 7.44386 5.0179 7.44386C3.96122 7.44386 3.10461 6.58725 3.10461 5.53056C3.10461 4.47388 3.96122 3.61727 5.0179 3.61727Z"
						/><path
							class="icons-default-fill icons-unfilled"
							d="M12.4755 8.01419C12.9883 8.01419 13.411 8.40023 13.4687 8.89757L13.4755 9.01419V13.3816C13.4755 15.3059 11.9155 16.8658 9.99118 16.8658C8.131 16.8658 6.61129 15.4081 6.51205 13.5727L6.50689 13.3816V9.01419C6.50689 8.50135 6.89293 8.07868 7.39027 8.02092L7.50689 8.01419H12.4755ZM12.4755 9.01419H7.50689V13.3816C7.50689 14.7536 8.61914 15.8658 9.99118 15.8658C11.3083 15.8658 12.3861 14.8408 12.4702 13.5449L12.4755 13.3816V9.01419ZM5.7748 8.01359C5.63281 8.25885 5.54142 8.53706 5.5149 8.83394L5.50689 9.01419H3.01758V12.7533C3.01758 13.7785 3.84866 14.6096 4.87385 14.6096C5.14507 14.6096 5.40269 14.5514 5.63495 14.4469C5.7142 14.7755 5.83078 15.0906 5.97923 15.387C5.6396 15.5306 5.26595 15.6096 4.87385 15.6096C3.35271 15.6096 2.1093 14.4205 2.02243 12.9211L2.01758 12.7533V9.01419C2.01758 8.50135 2.40362 8.07868 2.90096 8.02092L3.01758 8.01419L5.7748 8.01359ZM14.2076 8.01359L16.9919 8.01419C17.5047 8.01419 17.9274 8.40023 17.9852 8.89757L17.9919 9.01419V12.7541C17.9919 14.3311 16.7135 15.6096 15.1364 15.6096C14.7355 15.6096 14.3539 15.527 14.0077 15.3778C14.1559 15.0801 14.2717 14.7647 14.351 14.435C14.5894 14.5472 14.8556 14.6096 15.1364 14.6096C16.1124 14.6096 16.9124 13.8561 16.9863 12.8991L16.9919 12.7541V9.01419H14.4755L14.47 8.86493C14.4472 8.55642 14.3545 8.26737 14.2076 8.01359ZM9.98931 2.98914C11.2194 2.98914 12.2167 3.98636 12.2167 5.2165C12.2167 6.44664 11.2194 7.44386 9.98931 7.44386C8.75917 7.44386 7.76194 6.44664 7.76194 5.2165C7.76194 3.98636 8.75917 2.98914 9.98931 2.98914ZM14.9765 3.61727C16.0332 3.61727 16.8898 4.47388 16.8898 5.53056C16.8898 6.58725 16.0332 7.44386 14.9765 7.44386C13.9198 7.44386 13.0632 6.58725 13.0632 5.53056C13.0632 4.47388 13.9198 3.61727 14.9765 3.61727ZM5.0179 3.61727C6.07459 3.61727 6.9312 4.47388 6.9312 5.53056C6.9312 6.58725 6.07459 7.44386 5.0179 7.44386C3.96122 7.44386 3.10461 6.58725 3.10461 5.53056C3.10461 4.47388 3.96122 3.61727 5.0179 3.61727ZM9.98931 3.98914C9.31145 3.98914 8.76194 4.53864 8.76194 5.2165C8.76194 5.89435 9.31145 6.44386 9.98931 6.44386C10.6672 6.44386 11.2167 5.89435 11.2167 5.2165C11.2167 4.53864 10.6672 3.98914 9.98931 3.98914ZM14.9765 4.61727C14.4721 4.61727 14.0632 5.02616 14.0632 5.53056C14.0632 6.03496 14.4721 6.44386 14.9765 6.44386C15.4809 6.44386 15.8898 6.03496 15.8898 5.53056C15.8898 5.02616 15.4809 4.61727 14.9765 4.61727ZM5.0179 4.61727C4.51351 4.61727 4.10461 5.02616 4.10461 5.53056C4.10461 6.03496 4.51351 6.44386 5.0179 6.44386C5.5223 6.44386 5.9312 6.03496 5.9312 5.53056C5.9312 5.02616 5.5223 4.61727 5.0179 4.61727Z"
						/></svg
					>
				</mentionchannelicon>
			{/if}
		</originalmessage>
		<replysection>
			{#if message.replies.length > 0}
				<replyexpander on:click={() => (repliesExpanded = !repliesExpanded)}>
					<svg
						viewBox="-10 -10 32 32"
						class="app-svg icons-triangle-down-small {repliesExpanded
							? 'triangle-expanded'
							: ''}"
						><path
							class="icons-default-fill"
							d="M3.07615 4.61732C3.23093 4.24364 3.59557 4 4.00003 4H8.00003C8.40449 4 8.76913 4.24364 8.92391 4.61732C9.07869 4.99099 8.99313 5.42111 8.70714 5.70711L6.70714 7.70711C6.31661 8.09763 5.68345 8.09763 5.29292 7.70711L3.29292 5.70711C3.00692 5.42111 2.92137 4.99099 3.07615 4.61732Z"
						/></svg
					>
					<p>
						{#if repliesExpanded}Collapse all{:else}{message.replies.length} repl{message
								.replies.length === 1
								? 'y'
								: 'ies'} by {replyUsers}
						{/if}
					</p>
				</replyexpander>{/if}
			{#if repliesExpanded}
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
								<p class="sendername">
									{reply.user.firstname ?? ''}
									{reply.user.lastname ?? ''}
								</p>
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
				{/each}{/if}
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
		position: relative;
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

	mentionchannelicon {
		position: absolute;
		top: 10px;
		right: -16px;
		border-radius: 999px;
		background-color: #cc4a31;
		width: 32px;
		height: 32px;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	mentionchannelicon svg {
		width: 32px;
		scale: 120%;
	}

	mentionchannelicon svg .icons-filled {
		display: none;
	}

	mentionchannelicon svg .icons-unfilled {
		fill: white;
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

	replyexpander {
		display: flex;
		align-items: center;
	}

	replyexpander svg.icons-triangle-down-small {
		width: 30px;
		fill: var(--mspurple);
		transform: rotate(-90deg);
		visibility: hidden;
	}

	replyexpander:hover svg.icons-triangle-down-small {
		visibility: visible;
	}

	replyexpander svg.icons-triangle-down-small.triangle-expanded {
		visibility: visible;
		width: 30px;
		transform: rotate(0deg);
		fill: var(--mspurple);
	}

	replyexpander p {
		margin-block-start: 0;
		margin-block-end: 0;
		color: var(--mspurple);
		font-size: 12px;
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

		replyexpander svg.icons-triangle-down-small {
			fill: var(--mspurpledarkmode);
		}

		replyexpander svg.icons-triangle-down-small.triangle-expanded {
			fill: var(--mspurpledarkmode);
		}

		replyexpander p {
			color: var(--mspurpledarkmode);
		}

		/*background-color: var(--mspurpledarkmode);*/
	}
</style>

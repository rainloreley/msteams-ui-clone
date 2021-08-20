<script>
	import MSTTeamChatPostCell from '../components/MSTTeamChatPostCell.svelte';
	import md5 from 'md5';
	import MenuDots from '../components/MenuDots.svelte';

	export let channeldata;
</script>

<mschannelview>
	{#if channeldata !== undefined}
		<channelheader>
			<leftside>
				<teamimagewrapper>
					<img
						src="https://source.boringavatars.com/marble/100/{md5(
							channeldata.team.name
						)}?colors=92A1C6,146A7C,F0AB3D,C271B4,C20D90"
						alt="team icon"
					/>
				</teamimagewrapper>
				<h2>{channeldata.channel.name}</h2>
				<channeltabmenu>
					<button class="selected">
						<p>Posts</p>
					</button>
					<button>
						<p>Files</p>
					</button>
					<button>
						<p>Class Notebook</p>
					</button>
					<button>
						<p>Assignments</p>
					</button>
					<button>
						<p>Grades</p>
					</button>
				</channeltabmenu>
			</leftside>
			<rightside>
				<button class="start-videocall">
					<svg
						role="presentation"
						viewBox="-6 -6 32 32"
						class="app-svg icons-call-meetup-line"
						><g class="icons-default-fill"
							><path
								class="icons-unfilled"
								d="M4.5 4C3.11929 4 2 5.11929 2 6.5V13.5C2 14.8807 3.11929 16 4.5 16H11.5C12.8807 16 14 14.8807 14 13.5V12.5L16.4 14.3C17.0592 14.7944 18 14.324 18 13.5V6.49998C18 5.67594 17.0592 5.20556 16.4 5.69998L14 7.49998V6.5C14 5.11929 12.8807 4 11.5 4H4.5ZM14 8.74998L17 6.49998V13.5L14 11.25V8.74998ZM13 6.5V13.5C13 14.3284 12.3284 15 11.5 15H4.5C3.67157 15 3 14.3284 3 13.5V6.5C3 5.67157 3.67157 5 4.5 5H11.5C12.3284 5 13 5.67157 13 6.5Z"
								><path
									class="icons-filled"
									d="M13 6.5C13 5.11929 11.8807 4 10.5 4H4.5C3.11929 4 2 5.11929 2 6.5V13.5C2 14.8807 3.11929 16 4.5 16H10.5C11.8807 16 13 14.8807 13 13.5V6.5ZM14 7.93082V12.0815L16.7642 14.4319C17.2512 14.8461 18 14.4999 18 13.8606V6.19315C18 5.55685 17.2575 5.20962 16.7692 5.61756L14 7.93082Z"
								/></path
							></g
						></svg
					>
					<p>Meet</p>
				</button>

				<svg
					viewBox="-6 -6 32 32"
					role="presentation"
					class="app-svg icons-info"
					><g class="icons-default-fill"
						><path
							class="icons-filled"
							d="M10.0488 2.04871C14.4671 2.04871 18.0488 5.63043 18.0488 10.0487C18.0488 14.467 14.4671 18.0487 10.0488 18.0487C5.63055 18.0487 2.04883 14.467 2.04883 10.0487C2.04883 5.63043 5.63055 2.04871 10.0488 2.04871ZM10.0001 8.49999C9.75465 8.49999 9.55051 8.67687 9.50817 8.91012L9.50011 8.99999V13.5021L9.50817 13.592C9.55051 13.8253 9.75465 14.0021 10.0001 14.0021C10.2456 14.0021 10.4497 13.8253 10.4921 13.592L10.5001 13.5021V8.99999L10.4921 8.91012C10.4497 8.67687 10.2456 8.49999 10.0001 8.49999ZM10.0001 5.99999C9.5859 5.99999 9.25011 6.33578 9.25011 6.74999C9.25011 7.16421 9.5859 7.49999 10.0001 7.49999C10.4143 7.49999 10.7501 7.16421 10.7501 6.74999C10.7501 6.33578 10.4143 5.99999 10.0001 5.99999Z"
						/><path
							class="icons-unfilled"
							d="M10.0488 2.04871C14.4671 2.04871 18.0488 5.63043 18.0488 10.0487C18.0488 14.467 14.4671 18.0487 10.0488 18.0487C5.63055 18.0487 2.04883 14.467 2.04883 10.0487C2.04883 5.63043 5.63055 2.04871 10.0488 2.04871ZM10.0488 3.04871C6.18283 3.04871 3.04883 6.18271 3.04883 10.0487C3.04883 13.9147 6.18283 17.0487 10.0488 17.0487C13.9148 17.0487 17.0488 13.9147 17.0488 10.0487C17.0488 6.18271 13.9148 3.04871 10.0488 3.04871ZM10.0001 8.49999C10.2456 8.49999 10.4497 8.67687 10.4921 8.91012L10.5001 8.99999V13.5021C10.5001 13.7783 10.2763 14.0021 10.0001 14.0021C9.75465 14.0021 9.55051 13.8253 9.50817 13.592L9.50011 13.5021V8.99999C9.50011 8.72385 9.72397 8.49999 10.0001 8.49999ZM10.0488 5.99999C10.463 5.99999 10.7988 6.33578 10.7988 6.74999C10.7988 7.16421 10.463 7.49999 10.0488 7.49999C9.63461 7.49999 9.29883 7.16421 9.29883 6.74999C9.29883 6.33578 9.63461 5.99999 10.0488 5.99999Z"
						/></g
					></svg
				>
				<svg
					viewBox="-6 -6 32 32"
					class="menudots"
					focusable="false"
					role="presentation"><MenuDots /></svg
				>
			</rightside>
		</channelheader>

		<mstteamchat>
			<messageslist>
				{#each channeldata.channel.messages as message}
					<MSTTeamChatPostCell {message} />
				{/each}
				<!--<MSTTeamChatPostCell
					message={{
						user: loggedinuser,
						timestamp: 1629394402,
						message:
							'<font style="color: var(--mspurple);">General</font>, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer vitae mattis lectus. Fusce at finibus dui. Nam scelerisque orci magna, nec porttitor turpis mattis at. Sed ultrices elit quam, nec aliquet magna egestas efficitur. Integer venenatis est id metus bibendum pretium. Praesent at urna eu orci molestie molestie sed non orci. Vestibulum eu dui sed orci sollicitudin aliquet vitae eu ante. Quisque vitae rutrum nulla, sed fringilla lectus. In facilisis nibh nisl, vel dignissim erat molestie ut. Aenean at massa et leo finibus accumsan. Phasellus congue quis libero sit amet sodales. Donec ultricies commodo quam, vel eleifend purus dignissim vitae. Nam laoreet, sem a volutpat interdum, nibh quam faucibus est, sit amet hendrerit ligula augue quis nunc. Duis a lacus tellus. ',
						title: 'A very important message',
						postedbyme: true,
						mentionschannel: true,
						replies: [
							{
								user: {
									name: 'Barack Obama',
									pfp: 'https://www.whitehouse.gov/wp-content/uploads/2021/01/44_barack_obama.jpg',
									status: 'dnd',
								},
								timestamp: 1629394978,
								message: 'wow, so much text',
								postedbyme: false,
							},
							{
								user: {
									name: 'Tim Cook',
									pfp: 'https://pbs.twimg.com/profile_images/1403556543098916872/83tVAzyy.jpg',
									status: 'away',
								},
								timestamp: 1629395278,
								message: 'why am I even here?!',
							},
						],
					}}
				/>-->
				<button class="new-conversation">
					<newconversationbutton>
						<svg
							viewBox="-6 -6 32 32"
							class="app-svg icons-compose"
							focusable="false"
							role="presentation"
							><g class="icons-default-fill"
								><path
									class="icons-filled"
									d="M6.50061 4.00172L10.9998 4.00057C11.414 4.00057 11.7499 4.33617 11.75 4.75038C11.7501 5.13008 11.468 5.44394 11.102 5.4937L11.0002 5.50057L6.51667 5.50155C6.13457 5.50964 6.01046 5.53716 5.87106 5.61171C5.75732 5.67254 5.67254 5.75732 5.61171 5.87106C5.55823 5.97107 5.52714 6.06976 5.51189 6.26194L5.50459 6.38922L5.5 6.67272L5.50155 13.4833C5.50964 13.8654 5.53716 13.9895 5.61171 14.1289C5.67254 14.2427 5.75732 14.3275 5.87106 14.3883C5.97107 14.4418 6.06976 14.4729 6.26199 14.4881L6.38931 14.4954L6.67291 14.5H13.3271L13.6107 14.4954C13.8908 14.4844 14.0089 14.4525 14.1289 14.3883C14.2427 14.3275 14.3275 14.2427 14.3883 14.1289C14.4418 14.0289 14.4729 13.9302 14.4881 13.738L14.4954 13.6107L14.5 13.3271V9C14.5 8.58579 14.8358 8.25 15.25 8.25C15.6297 8.25 15.9435 8.53215 15.9932 8.89823L16 9V13.3271C16 14.0499 15.9256 14.435 15.711 14.8363C15.5104 15.2115 15.2115 15.5104 14.8363 15.711C14.4796 15.9018 14.1357 15.9817 13.556 15.9972L13.3271 16H6.67291C5.95008 16 5.56498 15.9256 5.16367 15.711C4.78852 15.5104 4.48962 15.2115 4.28899 14.8363C4.11447 14.51 4.03344 14.1957 4.00851 13.6959L4.00172 13.4994L4 6.67291C4 5.95008 4.07437 5.56498 4.28899 5.16367C4.48962 4.78852 4.78852 4.48962 5.16367 4.28899C5.48998 4.11447 5.80427 4.03344 6.30409 4.00851L6.50061 4.00172L10.9998 4.00057L6.50061 4.00172ZM9.35355 9.58363L15.7175 3.21967C16.0104 2.92678 16.4853 2.92678 16.7782 3.21967C17.0444 3.48594 17.0686 3.9026 16.8508 4.19621L16.7782 4.28033L10.4142 10.6443L9 10.9978L9.35355 9.58363L15.7175 3.21967L9.35355 9.58363Z"
								/><path
									class="icons-unfilled"
									d="M11.5 4C11.7761 4 12 4.22386 12 4.5C12 4.77614 11.7761 5 11.5 5H6.5C5.67157 5 5 5.67157 5 6.5V13.5C5 14.3284 5.67157 15 6.5 15H13.5C14.3284 15 15 14.3284 15 13.5V8.5C15 8.22386 15.2239 8 15.5 8C15.7761 8 16 8.22386 16 8.5V13.5C16 14.8807 14.8807 16 13.5 16H6.5C5.11929 16 4 14.8807 4 13.5V6.5C4 5.11929 5.11929 4 6.5 4H11.5ZM16.1514 2.85355C16.3467 2.65829 16.6632 2.65829 16.8585 2.85355C17.0538 3.04882 17.0538 3.3654 16.8585 3.56066L9.78744 10.6317L8.90355 10.8085L9.08033 9.92462L16.1514 2.85355Z"
								/></g
							></svg
						>
						<p>New conversation</p>
					</newconversationbutton>
				</button>
			</messageslist>
		</mstteamchat>
	{/if}
</mschannelview>

<style>
	mschannelview {
		background-color: var(--ms-chatbg);
		width: calc(100% - 360px - 66px);
		display: flex;
		flex-direction: column;
	}

	mstteamchat {
		background-color: var(--ms-chatbg);
		width: 100%;
		height: calc(100% - 60px);
		display: flex;
		justify-content: center;
	}

	channelheader {
		height: 60px;
		border-bottom: 1.5px solid #ebebeb;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	channelheader leftside {
		height: 100%;
		display: flex;
		align-items: center;
	}

	channelheader leftside h2 {
		font-size: 18px;
		margin-left: 16px;
	}

	teamimagewrapper {
		overflow: hidden;
		width: 30px;
		height: 30px;
		margin-left: 16px;
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 5px;
	}

	teamimagewrapper img {
		scale: 200%;
	}

	channeltabmenu {
		height: 100%;
		margin-left: 16px;
	}

	channeltabmenu button {
		height: 60px;
		border: none;
		background-color: transparent;
	}

	channeltabmenu button:hover {
		border-bottom: 3.5px solid #999;
	}

	channeltabmenu button p {
		color: #616161;
		font-size: 14px;
	}
	channeltabmenu button:hover p {
		color: #000;
	}

	channeltabmenu button.selected {
		border-bottom: 3.5px solid var(--mspurple);
	}

	channeltabmenu button.selected p {
		color: #242424;
		font-weight: 600;
	}

	channelheader rightside {
		display: flex;
		height: 100%;
		align-items: center;
	}

	channelheader rightside .menudots {
		width: 30px;
		fill: #616161;
		margin-right: 16px;
	}

	channelheader rightside .menudots:hover {
		fill: var(--mspurple);
	}

	channelheader rightside .icons-info {
		width: 35px;
	}

	channelheader rightside .icons-info .icons-filled {
		display: none;
	}

	channelheader rightside .icons-info .icons-unfilled {
		fill: #616161;
	}

	channelheader rightside .icons-info:hover .icons-filled {
		display: block;
		fill: var(--mspurple);
	}

	channelheader rightside .icons-info:hover .icons-unfilled {
		fill: var(--mspurple);
	}

	channelheader rightside .start-videocall {
		background-color: white;
		display: flex;
		border: 1px solid #cdcdcd;
		border-radius: 4px;
		width: 96px;
		height: 32px;
		margin-right: 16px;
		margin-block-start: 0px;
		margin-block-end: 0px;
		align-items: center;
		justify-content: center;
	}

	channelheader rightside .start-videocall:hover {
		background-color: #f5f5f5;
		border: 1px solid #bdbdbd;
	}

	channelheader rightside .start-videocall svg {
		width: 30px;
	}

	channelheader rightside .start-videocall p {
		font-size: 14px;
	}

	messageslist {
		width: 70%;
		position: relative;
		display: flex;
		flex-direction: column;
	}

	newconversationbutton {
		display: flex;
		justify-content: center;
		width: 100%;
		height: 100%;
		margin: 0;
	}

	newconversationbutton svg {
		width: 35px;
		align-self: center;
		fill: white;
	}

	newconversationbutton p {
		margin-block-start: 0;
		margin-block-end: 0;
		color: white;
		font-size: 14px;
		align-self: center;
		text-align: center;
		margin-right: 8px;
	}

	.new-conversation {
		position: absolute;
		bottom: 20px;
		left: 64px;
		width: 190px;
		height: 38px;
		border-radius: 6px;
		background-color: var(--mspurple);
		border: none;
	}

	.new-conversation:hover {
		background-color: #464775;
	}

	@media (prefers-color-scheme: dark) {
		mstteamchat {
			background-color: #202020;
		}

		mschannelview {
			background-color: #202020;
		}

		.new-conversation:hover {
			background-color: var(--mspurpledarkmode);
		}

		channelheader {
			border-bottom: 1.5px solid #000;
		}

		channelheader leftside h2 {
			color: white;
		}

		channeltabmenu button p {
			color: #adadad;
			font-size: 14px;
		}

		channeltabmenu button.selected {
			border-bottom: 3.5px solid var(--mspurpledarkmode);
		}

		channeltabmenu button:hover p {
			color: #eee;
		}

		channeltabmenu button.selected p {
			color: white;
		}

		channeltabmenu button:hover {
			border-bottom: 3.5px solid #777;
		}

		channelheader rightside .menudots {
			fill: #adadad;
		}

		channelheader rightside .menudots:hover {
			fill: var(--mspurpledarkmode);
		}

		channelheader rightside .icons-info .icons-unfilled {
			fill: #adadad;
		}

		channelheader rightside .icons-info:hover .icons-filled {
			fill: var(--mspurpledarkmode);
		}

		channelheader rightside .icons-info:hover .icons-unfilled {
			fill: var(--mspurpledarkmode);
		}

		channelheader rightside .start-videocall {
			background-color: #2a2a2a;
			border: 1px solid #5c5c5c;
			color: white;
		}

		channelheader rightside .start-videocall svg {
			fill: white;
		}

		channelheader rightside .start-videocall:hover {
			background-color: #202020;
			border: 1px solid #666;
		}
	}
</style>

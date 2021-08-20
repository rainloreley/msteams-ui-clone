<script>
	import msteamsdataset from './data/msteamsdataset.json';
	import ProfilePictureWithStatus from './components/ProfilePictureWithStatus.svelte';

	let profilecardvisible = false;
</script>

<mstheader>
	<headerleft>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			width="24"
			height="24"
			viewBox="0 0 24 24"
			fill="none"
			stroke="currentColor"
			stroke-width="1.5"
			stroke-linecap="round"
			stroke-linejoin="round"
			class="feather feather-chevron-left"
			><polyline points="15 18 9 12 15 6" /></svg
		>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			width="24"
			height="24"
			viewBox="0 0 24 24"
			fill="none"
			stroke="currentColor"
			stroke-width="1.5"
			stroke-linecap="round"
			stroke-linejoin="round"
			class="feather feather-chevron-right"
			><polyline points="9 18 15 12 9 6" /></svg
		>
	</headerleft>
	<headercenter>
		<searchfield>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				width="24"
				height="24"
				viewBox="0 0 24 24"
				fill="none"
				stroke="currentColor"
				stroke-width="2"
				stroke-linecap="round"
				stroke-linejoin="round"
				class="feather feather-search searchicon"
			>
				<circle cx="11" cy="11" r="8" />
				<line x1="21" y1="21" x2="16.65" y2="16.65" />
			</svg>
			<input placeholder="Search" />
		</searchfield>
	</headercenter>
	<headerright>
		<svg
			viewBox="-6 -6 32 32"
			class="menudots"
			focusable="false"
			role="presentation"
			><g class="icons-default-fill"
				><g class="icons-unfilled"
					><path
						d="M6.25 10C6.25 10.6904 5.69036 11.25 5 11.25C4.30964 11.25 3.75 10.6904 3.75 10C3.75 9.30964 4.30964 8.75 5 8.75C5.69036 8.75 6.25 9.30964 6.25 10Z"
					/><path
						d="M11.25 10C11.25 10.6904 10.6904 11.25 10 11.25C9.30964 11.25 8.75 10.6904 8.75 10C8.75 9.30964 9.30964 8.75 10 8.75C10.6904 8.75 11.25 9.30964 11.25 10Z"
					/><path
						d="M15 11.25C15.6904 11.25 16.25 10.6904 16.25 10C16.25 9.30964 15.6904 8.75 15 8.75C14.3096 8.75 13.75 9.30964 13.75 10C13.75 10.6904 14.3096 11.25 15 11.25Z"
					/></g
				><g class="icons-filled"
					><path
						d="M6.75 10C6.75 10.9665 5.9665 11.75 5 11.75C4.0335 11.75 3.25 10.9665 3.25 10C3.25 9.0335 4.0335 8.25 5 8.25C5.9665 8.25 6.75 9.0335 6.75 10Z"
					/><path
						d="M11.75 10C11.75 10.9665 10.9665 11.75 10 11.75C9.0335 11.75 8.25 10.9665 8.25 10C8.25 9.0335 9.0335 8.25 10 8.25C10.9665 8.25 11.75 9.0335 11.75 10Z"
					/><path
						d="M15 11.75C15.9665 11.75 16.75 10.9665 16.75 10C16.75 9.0335 15.9665 8.25 15 8.25C14.0335 8.25 13.25 9.0335 13.25 10C13.25 10.9665 14.0335 11.75 15 11.75Z"
					/></g
				></g
			></svg
		>
		<profilepicture on:click={() => (profilecardvisible = !profilecardvisible)}>
			<ProfilePictureWithStatus
				image={msteamsdataset.user.pfp}
				bgcolor={'#464775'}
				bgcolordark={'#0a0a0a'}
				size={'40'}
				status={msteamsdataset.user.status}
			/>
		</profilepicture>
		<!--<profilepicture>
			<innerpfp>
				<img src={msteamsdataset.user.pfp} alt="user profile" class="picture" />
				<svg
					id="Layer_1"
					data-name="Layer1"
					xmlns="http://www.w3.org/2000/svg"
					viewBox="009.99710.003"
				>
					<defs
						><style>
							.cls-1 {
								fill: #92c353;
							}
							.cls-2 {
								fill: #fff;
							}
						</style></defs
					>
					<title>1_Presence_Available_Light_theme_2_10px</title>
					<path
						class="cls-1"
						d="M6.311.176A5,5,0,0,1,9.82,3.689a4.944,4.944,0,0,1,0,2.622,5.233,5.233,0,0,1-.506,1.2A5.038,5.038,0,0,1,8.53,8.53a4.974,4.974,0,0,1-1.01.782,5.089,5.089,0,0,1-1.207.51,4.931,4.931,0,0,1-2.624,0,5.043,5.043,0,0,1-1.2-.511A4.807,4.807,0,0,1,1.47,8.53,4.907,4.907,0,0,1,.688,7.515a5.1,5.1,0,0,1-.51-1.2,4.931,4.931,0,0,1,0-2.624A5.03,5.03,0,0,1,2.488.68a5.214,5.214,0,0,1,1.2-.506,4.959,4.959,0,0,1,2.626,0Z"
						transform="translate(00.003)"
					/><path
						class="cls-2"
						d="M6.821,3.594a.514.514,0,0,1,.152.1.549.549,0,0,1,.1.152.425.425,0,0,1,.039.175.454.454,0,0,1-.136.332l-2.1,2.11a.471.471,0,0,1-.664,0l-.957-.957a.447.447,0,0,1-.137-.332A.419.419,0,0,1,3.159,5a.463.463,0,0,1,.1-.151.509.509,0,0,1,.151-.1.426.426,0,0,1,.176-.039.418.418,0,0,1,.327.137l.63.625L6.314,3.691a.45.45,0,0,1,.332-.136A.425.425,0,0,1,6.821,3.594Z"
						transform="translate(00.003)"
					/></svg
				>
			</innerpfp>
		</profilepicture>-->
	</headerright>
</mstheader>

<profilecardwrapper
	style={profilecardvisible ? 'display: flex' : 'display: none'}
	on:click={() => (profilecardvisible = false)}
>
	<profilecard>
		<profilecard-header>
			<ProfilePictureWithStatus
				image={msteamsdataset.user.pfp}
				bgcolor={'#fff'}
				bgcolordark={'#2a2a2a'}
				size={'60'}
				status={msteamsdataset.user.status}
			/>
			<profilecard-header-info>
				<p class="username">{msteamsdataset.user.name}</p>
				<p class="email">{msteamsdataset.user.email}</p>
			</profilecard-header-info>
		</profilecard-header>
		{#if typeof msteamsdataset.user.statusmessage === 'string'}
			<profilecard-statusmessage>
				<p>{msteamsdataset.user.statusmessage}</p>
			</profilecard-statusmessage>
		{/if}
		<section-saved>
			<button class="account-section-button">
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
					class="feather feather-bookmark"
					><path d="M19 21l-7-5-7 5V5a2 2 0 0 1 2-2h10a2 2 0 0 1 2 2z" /></svg
				>
				<p>Saved</p>
			</button>
		</section-saved>
		<section-account>
			<button class="account-section-button">
				<svg
					viewBox="-6 -6 32 32"
					role="presentation"
					focusable="false"
					class="app-svg icons-accounts-tab"
					><g class="icons-default-fill"
						><path
							d="M8 8.5C8 9.32843 7.32843 10 6.5 10C5.67157 10 5 9.32843 5 8.5C5 7.67157 5.67157 7 6.5 7C7.32843 7 8 7.67157 8 8.5Z"
						/><path
							d="M4 11.6988C4 11.1748 4.42479 10.75 4.94879 10.75H8.05121C8.57521 10.75 9 11.1748 9 11.6988C9 12.546 8.42338 13.2845 7.60144 13.49L7.54243 13.5048C6.85801 13.6759 6.14199 13.6759 5.45757 13.5048L5.39856 13.49C4.57661 13.2845 4 12.546 4 11.6988Z"
						/><path
							d="M11.5 8C11.2239 8 11 8.22386 11 8.5C11 8.77614 11.2239 9 11.5 9H14.5C14.7761 9 15 8.77614 15 8.5C15 8.22386 14.7761 8 14.5 8H11.5Z"
						/><path
							d="M11.5 11C11.2239 11 11 11.2239 11 11.5C11 11.7761 11.2239 12 11.5 12H14.5C14.7761 12 15 11.7761 15 11.5C15 11.2239 14.7761 11 14.5 11H11.5Z"
						/><path
							d="M2 5.75C2 4.7835 2.7835 4 3.75 4H16.25C17.2165 4 18 4.7835 18 5.75V14.25C18 15.2165 17.2165 16 16.25 16H3.75C2.7835 16 2 15.2165 2 14.25V5.75ZM3.75 5C3.33579 5 3 5.33579 3 5.75V14.25C3 14.6642 3.33579 15 3.75 15H16.25C16.6642 15 17 14.6642 17 14.25V5.75C17 5.33579 16.6642 5 16.25 5H3.75Z"
						/></g
					></svg
				>
				<p>Manage account</p>
			</button>

			<button class="account-section-button">
				<svg
					viewBox="-6 -6 32 32"
					class="app-svg icons-add"
					focusable="false"
					role="presentation"
					><g class="icons-default-fill"
						><path
							class="icons-filled"
							d="M9.25 16.25C9.25 16.6642 9.58579 17 10 17C10.4142 17 10.75 16.6642 10.75 16.25V10.75H16.25C16.6642 10.75 17 10.4142 17 10C17 9.58579 16.6642 9.25 16.25 9.25H10.75V3.75C10.75 3.33579 10.4142 3 10 3C9.58579 3 9.25 3.33579 9.25 3.75V9.25H3.75C3.33579 9.25 3 9.58579 3 10C3 10.4142 3.33579 10.75 3.75 10.75H9.25V16.25Z"
						/><path
							class="icons-unfilled"
							d="M9.5 16.5C9.5 16.7761 9.72386 17 10 17C10.2761 17 10.5 16.7761 10.5 16.5V10.5H16.5C16.7761 10.5 17 10.2761 17 10C17 9.72386 16.7761 9.5 16.5 9.5H10.5V3.5C10.5 3.22386 10.2761 3 10 3C9.72386 3 9.5 3.22386 9.5 3.5V9.5H3.5C3.22386 9.5 3 9.72386 3 10C3 10.2761 3.22386 10.5 3.5 10.5H9.5V16.5Z"
						/></g
					></svg
				>
				<p>Add personal account</p>
			</button>
		</section-account>
		<section-logout>
			<button class="account-section-button">
				<p class="text-noimage">Sign out</p>
			</button>
		</section-logout>
	</profilecard>
</profilecardwrapper>

<style>
	mstheader {
		display: flex;
		margin: 0 auto;
		background-color: #464775;
		/*justify-content: space-between;*/
		align-content: center;
		height: 48px;
		width: 100%;
	}

	headerright {
		display: flex;
		width: 426px;
		justify-content: flex-end;
	}

	headerright .menudots {
		width: 30px;
		margin-right: 8px;
	}

	headerright .menudots g {
		fill: white;
	}

	/*profilepicture {
		display: flex;
		justify-content: end;
	}*/

	headerright profilepicture {
		width: 40px;
		height: 100%;
		display: flex;
		padding-left: 10px;
		padding-right: 6px;
		margin-right: 8px;
		align-items: center;
		justify-content: center;
	}

	headerright profilepicture:hover {
		background-color: var(--mspurple);
	}

	/*headerright profilepicture innerpfp {
		height: 35px;
		width: 35px;
		display: block;
		position: relative;
		align-self: center;
	}*/

	headerright profilepicture innerpfp svg {
		position: absolute;
		height: 10px;
		width: 10px;
		bottom: 0;
		right: -5px;
	}

	/*headerright profilepicture .picture {
		border-radius: 999px;
		height: 100%;
		width: 40px;
		align-self: center;
	}*/

	.searchicon {
		align-self: center;
		color: gray;
		margin-left: 8px;
		height: 1.2em;
	}

	searchfield {
		background-color: #dddde5;
		display: flex;
		width: 100%;
		border-radius: 5px;
		align-self: center;
	}

	searchfield input {
		border: none;
		margin: 0px;
		width: 100%;
		background-color: transparent;
	}
	headercenter {
		align-self: center;
		height: 100%;
		width: calc(100% - (2 * 426px));
		display: flex;
	}

	headerleft {
		display: flex;
		width: 426px;
		justify-content: flex-end;
		padding-right: 8px;
	}

	headerleft svg {
		align-self: center;
	}

	headerleft svg {
		color: #dddddd;
	}

	profilecardwrapper {
		position: absolute;
		height: 100%;
		width: 100%;
		z-index: 1;
	}

	profilecard {
		position: absolute;
		min-width: 350px;
		/*width: 200px;
		height: 60px;*/
		background-color: white;
		top: 4px;
		right: 4px;
		box-shadow: 0 0.2rem 0.4rem -0.075rem rgba(0, 0, 0, 0.1);
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	profilecard-header {
		display: flex;
		margin: 12px;
		width: 100%;
		padding-left: 16px;
		padding-top: 8px;
		/*justify-content: center;*/
		align-items: center;
		margin-bottom: 20px;
	}

	profilecard-header-info {
		display: flex;
		flex-direction: column;
	}

	profilecard-header-info p {
		margin-block-start: 0;
		margin-block-end: 0;
	}

	profilecard-header-info .username {
		font-weight: 600;
	}

	profilecard-header-info .email {
		color: gray;
		font-size: 12px;
	}

	profilecard-statusmessage {
		display: flex;
		width: 90%;
		min-width: 250px;
		margin-left: 8px;
		margin-right: 8px;
		background-color: #faf9f8;
		justify-content: start;
		align-items: flex-start;
		/*height: 50px;*/
	}

	profilecard-statusmessage p {
		margin-block-start: 0;
		margin-block-end: 0;
		margin: 8px 8px 24px 8px;
		font-size: 14px;
	}

	section-saved {
		margin-top: 16px;
		border-top: 2px solid #f3f2f1;
		width: 100%;
		height: 38px;
	}

	section-account {
		margin-top: 8px;
		border-top: 2px solid #f3f2f1;
		width: 100%;
		height: calc(38px * 2);
	}

	section-logout {
		margin-top: 8px;
		border-top: 2px solid #f3f2f1;
		width: 100%;
	}

	/*section-saved .saved-button {
		border: none;
		display: flex;
		background-color: transparent;
		width: 100%;
		padding-left: 8px;
		margin-top: 8px;
		height: 30px;
		margin-bottom: 8px;
		justify-content: start;
		align-items: center;
	}

	section-saved .saved-button:hover {
		background-color: #f0efee;
	}

	section-saved .saved-button p {
		margin-block-start: 0;
		margin-block-end: 0;
		font-size: 14px;
		margin-left: 8px;
	}

	section-saved .saved-button svg {
		display: block;
		width: 17px;
		height: 17px;
	}*/

	.account-section-button {
		border: none;
		display: flex;
		background-color: transparent;
		width: 100%;
		padding-left: 12px;
		margin-top: 8px;
		height: 30px;
		margin-bottom: 8px;
		justify-content: start;
		align-items: center;
	}

	.account-section-button:hover {
		background-color: #f0efee;
	}

	.account-section-button p {
		margin-block-start: 0;
		margin-block-end: 0;
		font-size: 14px;
		left: 35px;
		position: absolute;
	}

	.account-section-button p.text-noimage {
		left: 16px;
	}

	.account-section-button svg.feather {
		display: block;
		width: 17px;
		height: 17px;
	}

	.account-section-button svg.app-svg {
		display: block;
		width: 17px !important;
		height: 17px;
		scale: 180%;
	}

	@media (prefers-color-scheme: dark) {
		mstheader {
			background-color: #0a0a0a;
		}
		searchfield {
			background-color: #202020;
		}

		searchfield input::placeholder {
			color: white;
			opacity: 0.4;
		}

		headerright profilepicture:hover {
			background-color: #252525;
		}

		profilecard {
			background-color: #2a2a2a;
			box-shadow: 0 0.2rem 0.4rem -0.075rem rgba(0, 0, 0, 0.6);
		}

		profilecard-header-info .username {
			color: white;
		}

		profilecard-header-info .email {
			color: #adadad;
		}

		profilecard-statusmessage {
			background-color: #3b3a3a;
		}

		profilecard-statusmessage p {
			color: white;
		}

		section-saved {
			border-top: 2px solid #1f1f1f;
		}

		section-account {
			border-top: 2px solid #1f1f1f;
		}

		section-logout {
			border-top: 2px solid #1f1f1f;
		}

		.account-section-button:hover {
			background-color: #3b3a39;
		}

		.account-section-button p {
			color: #d6d6d6;
		}

		.account-section-button svg.feather {
			stroke: #d6d6d6;
		}

		.account-section-button svg.app-svg {
			fill: #d6d6d6;
		}
	}
</style>

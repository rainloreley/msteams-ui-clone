<script>
	export var image;
	export var bgcolor;
	export var bgcolordark;
	export var size;
	export var status;
</script>

<profilepicture style="width: {size}px; height: {size}px">
	<innerpfp style="width: {size}px; height: {size}px">
		<img
			src={image}
			alt="user profile"
			class="picture"
			style="width: {size}px; height: {size}px"
		/>
		{#if status == 'online'}
			<svg
				id="Layer_1"
				data-name="Layer1"
				xmlns="http://www.w3.org/2000/svg"
				viewBox="009.99710.003"
				style="border: 2px solid {window.matchMedia(
					'(prefers-color-scheme: dark)'
				).matches
					? bgcolordark
					: bgcolor}; @media (prefers-color-scheme: dark)"
			>
				<defs
					><style>
						.cls-online-1 {
							fill: #92c353;
						}
						.cls-online-2 {
							fill: #fff;
						}
					</style></defs
				>
				<path
					class="cls-online-1"
					d="M6.311.176A5,5,0,0,1,9.82,3.689a4.944,4.944,0,0,1,0,2.622,5.233,5.233,0,0,1-.506,1.2A5.038,5.038,0,0,1,8.53,8.53a4.974,4.974,0,0,1-1.01.782,5.089,5.089,0,0,1-1.207.51,4.931,4.931,0,0,1-2.624,0,5.043,5.043,0,0,1-1.2-.511A4.807,4.807,0,0,1,1.47,8.53,4.907,4.907,0,0,1,.688,7.515a5.1,5.1,0,0,1-.51-1.2,4.931,4.931,0,0,1,0-2.624A5.03,5.03,0,0,1,2.488.68a5.214,5.214,0,0,1,1.2-.506,4.959,4.959,0,0,1,2.626,0Z"
					transform="translate(00.003)"
				/><path
					class="cls-online-2"
					d="M6.821,3.594a.514.514,0,0,1,.152.1.549.549,0,0,1,.1.152.425.425,0,0,1,.039.175.454.454,0,0,1-.136.332l-2.1,2.11a.471.471,0,0,1-.664,0l-.957-.957a.447.447,0,0,1-.137-.332A.419.419,0,0,1,3.159,5a.463.463,0,0,1,.1-.151.509.509,0,0,1,.151-.1.426.426,0,0,1,.176-.039.418.418,0,0,1,.327.137l.63.625L6.314,3.691a.45.45,0,0,1,.332-.136A.425.425,0,0,1,6.821,3.594Z"
					transform="translate(00.003)"
				/></svg
			>
		{:else if status == 'away'}
			<svg
				xmlns="http://www.w3.org/2000/svg"
				xmlns:xlink="http://www.w3.org/1999/xlink"
				version="1.1"
				x="0px"
				y="0px"
				viewBox="0 0 12 12"
				enable-background="new 0 0 12 12"
				xml:space="preserve"
				style="border: 2px solid {window.matchMedia(
					'(prefers-color-scheme: dark)'
				).matches
					? bgcolordark
					: bgcolor}; @media (prefers-color-scheme: dark)"
				><g
					><g><circle fill="#FDB913" cx="6" cy="6" r="6" /></g><polyline
						fill="none"
						stroke="#FFFFFF"
						stroke-width="1.5"
						stroke-miterlimit="10"
						points="6,2 6,6 8.5,8.5"
					/></g
				></svg
			>
		{:else if status == 'dnd'}
			<svg
				id="Layer_1"
				data-name="Layer 1"
				xmlns="http://www.w3.org/2000/svg"
				viewBox="0 0 10 10"
				style="border: 2px solid {window.matchMedia(
					'(prefers-color-scheme: dark)'
				).matches
					? bgcolordark
					: bgcolor}; @media (prefers-color-scheme: dark)"
				><defs
					><style>
						.cls-dnd-1 {
							fill: #c4314b;
						}
						.cls-dnd-2 {
							fill: #fff;
						}
					</style></defs
				><path
					class="cls-dnd-1"
					d="M6.311.176A5.057,5.057,0,0,1,7.52.684a5.009,5.009,0,0,1,2.3,3.005,4.944,4.944,0,0,1,0,2.622,5.258,5.258,0,0,1-.506,1.2A5.079,5.079,0,0,1,8.53,8.53a4.94,4.94,0,0,1-1.011.782,5.1,5.1,0,0,1-1.206.51,4.924,4.924,0,0,1-2.624,0,5.042,5.042,0,0,1-1.2-.511A4.819,4.819,0,0,1,1.47,8.53,4.883,4.883,0,0,1,.688,7.515a5.1,5.1,0,0,1-.51-1.2,4.928,4.928,0,0,1,0-2.625A5.1,5.1,0,0,1,.688,2.48,4.961,4.961,0,0,1,1.47,1.47,5.015,5.015,0,0,1,2.485.684a5.214,5.214,0,0,1,1.2-.506A4.839,4.839,0,0,1,5,0,4.917,4.917,0,0,1,6.311.176Z"
				/><rect class="cls-dnd-2" x="3" y="4.5" width="4" height="1" /></svg
			>
		{/if}
	</innerpfp>
</profilepicture>

<style>
	profilepicture {
		/*width: 40px;
		height: 40px;*/
		display: flex;
		padding-left: 8px;
		padding-right: 8px;
		margin-right: 8px;
	}

	profilepicture innerpfp {
		/*height: 40px;
		width: 40px;*/
		display: block;
		position: relative;
		align-self: center;
	}

	profilepicture innerpfp svg {
		position: absolute;
		height: 10px;
		border-radius: 999px;
		width: 10px;
		bottom: 0;
		right: 0px;
	}

	profilepicture .picture {
		border-radius: 999px;
		height: 100%;
		/*width: 40px;*/
		align-self: center;
	}
</style>

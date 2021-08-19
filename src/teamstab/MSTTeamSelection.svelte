<script>
	import MenuDots from '../components/MenuDots.svelte';
	import MSTTeamSelectionItem from './MSTTeamSelectionItem.svelte';
</script>

<mstteamselection class="app-trailing-shadow">
	<header>
		<h2>Teams</h2>
		<svg
			viewBox="-6 -6 32 32"
			class="app-svg icons-filter"
			focusable="false"
			role="presentation"
			><g class="icons-default-fill"
				><path
					class="icons-filled"
					d="M12.25 13.5C12.6642 13.5 13 13.8358 13 14.25C13 14.6642 12.6642 15 12.25 15H7.75C7.33579 15 7 14.6642 7 14.25C7 13.8358 7.33579 13.5 7.75 13.5H12.25ZM14.25 9.25C14.6642 9.25 15 9.58579 15 10C15 10.4142 14.6642 10.75 14.25 10.75H5.75C5.33579 10.75 5 10.4142 5 10C5 9.58579 5.33579 9.25 5.75 9.25H14.25ZM16.25 5C16.6642 5 17 5.33579 17 5.75C17 6.16421 16.6642 6.5 16.25 6.5H3.75C3.33579 6.5 3 6.16421 3 5.75C3 5.33579 3.33579 5 3.75 5H16.25Z"
				/><path
					class="icons-unfilled"
					d="M7.5 13H12.5C12.7761 13 13 13.2239 13 13.5C13 13.7455 12.8231 13.9496 12.5899 13.9919L12.5 14H7.5C7.22386 14 7 13.7761 7 13.5C7 13.2545 7.17688 13.0504 7.41012 13.0081L7.5 13H12.5H7.5ZM5.5 9H14.5C14.7761 9 15 9.22386 15 9.5C15 9.74546 14.8231 9.94961 14.5899 9.99194L14.5 10H5.5C5.22386 10 5 9.77614 5 9.5C5 9.25454 5.17688 9.05039 5.41012 9.00806L5.5 9H14.5H5.5ZM3.5 5H16.5C16.7761 5 17 5.22386 17 5.5C17 5.74546 16.8231 5.94961 16.5899 5.99194L16.5 6H3.5C3.22386 6 3 5.77614 3 5.5C3 5.25454 3.17688 5.05039 3.41012 5.00806L3.5 5H16.5H3.5Z"
				/></g
			></svg
		>
	</header>
	<teamlist>
		<ul class="list-teams">
			<MSTTeamSelectionItem
				name={'Apple'}
				channelsvisible={true}
				channels={[
					{ name: 'General', selected: false },
					{ name: 'WWDC 22', selected: false },
					{ name: 'September Event', selected: false },
					{ name: 'iPhone 9999', selected: false },
					{ name: 'Apple Glasses', selected: false },
				]}
			/>
			<MSTTeamSelectionItem
				name={'Google'}
				channelsvisible={false}
				channels={[
					{ name: 'General', selected: false },
					{ name: 'Gmail', selected: false },
					{ name: 'Google Docs', selected: false },
					{ name: 'Search', selected: false },
					{ name: 'AI', selected: false },
					{ name: 'Quantum Computing', selected: false },
					{ name: 'Coffee Break', selected: false },
				]}
			/>
			<MSTTeamSelectionItem
				name="Microsoft"
				channelsvisible={true}
				channels={[
					{ name: 'General', selected: true },
					{ name: 'Azure', selected: false },
					{ name: 'Microsoft 365', selected: false },
					{ name: 'Secret Project', selected: false },
					{ name: 'Surface', selected: false },
					{ name: 'Cloud Computing', selected: false },
					{ name: 'Microsoft Teams', selected: false },
				]}
			/>
		</ul>
	</teamlist>
	<footer>
		<footerleft>
			<svg
				viewBox="-6 -6 32 32"
				role="presentation"
				class="app-svg icons-team-operation icons-team-create"
				focusable="false"
				><g class="icons-default-fill icons-filled"
					><path
						d="M11 10C11.1035 10 11.2052 10.0079 11.3045 10.023C9.90933 11.0206 9 12.6541 9 14.5C9 15.3244 9.1814 16.1065 9.50646 16.8085C8.90367 16.9334 8.23233 17 7.5 17C4.08805 17 2 15.5544 2 13.5V12C2 10.8954 2.89543 10 4 10H11Z"
					/><path
						d="M17 6.5C17 7.88071 15.8807 9 14.5 9C13.1193 9 12 7.88071 12 6.5C12 5.11929 13.1193 4 14.5 4C15.8807 4 17 5.11929 17 6.5Z"
					/><path
						d="M7.5 2C9.433 2 11 3.567 11 5.5C11 7.433 9.433 9 7.5 9C5.567 9 4 7.433 4 5.5C4 3.567 5.567 2 7.5 2Z"
					/><path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M19 14.5C19 16.9853 16.9853 19 14.5 19C12.0147 19 10 16.9853 10 14.5C10 12.0147 12.0147 10 14.5 10C16.9853 10 19 12.0147 19 14.5ZM15 12.5C15 12.2239 14.7761 12 14.5 12C14.2239 12 14 12.2239 14 12.5V14H12.5C12.2239 14 12 14.2239 12 14.5C12 14.7761 12.2239 15 12.5 15H14V16.5C14 16.7761 14.2239 17 14.5 17C14.7761 17 15 16.7761 15 16.5V15H16.5C16.7761 15 17 14.7761 17 14.5C17 14.2239 16.7761 14 16.5 14H15V12.5Z"
					/></g
				><g class="icons-default-fill icons-unfilled"
					><path
						d="M11 10C11.1035 10 11.2052 10.0079 11.3045 10.023C10.9143 10.302 10.5621 10.6308 10.2572 11H4C3.44772 11 3 11.4477 3 12V13.5C3 14.9071 4.57862 16 7.5 16C8.11725 16 8.67455 15.9512 9.16969 15.861C9.25335 16.1896 9.36661 16.5065 9.50646 16.8085C8.90367 16.9334 8.23233 17 7.5 17C4.08805 17 2 15.5544 2 13.5V12C2 10.8954 2.89543 10 4 10H11Z"
					/><path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M17 6.5C17 7.88071 15.8807 9 14.5 9C13.1193 9 12 7.88071 12 6.5C12 5.11929 13.1193 4 14.5 4C15.8807 4 17 5.11929 17 6.5ZM14.5 5C13.6716 5 13 5.67157 13 6.5C13 7.32843 13.6716 8 14.5 8C15.3284 8 16 7.32843 16 6.5C16 5.67157 15.3284 5 14.5 5Z"
					/><path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M7.5 2C9.433 2 11 3.567 11 5.5C11 7.433 9.433 9 7.5 9C5.567 9 4 7.433 4 5.5C4 3.567 5.567 2 7.5 2ZM7.5 3C6.11929 3 5 4.11929 5 5.5C5 6.88071 6.11929 8 7.5 8C8.88071 8 10 6.88071 10 5.5C10 4.11929 8.88071 3 7.5 3Z"
					/><path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M19 14.5C19 16.9853 16.9853 19 14.5 19C12.0147 19 10 16.9853 10 14.5C10 12.0147 12.0147 10 14.5 10C16.9853 10 19 12.0147 19 14.5ZM15 12.5C15 12.2239 14.7761 12 14.5 12C14.2239 12 14 12.2239 14 12.5V14H12.5C12.2239 14 12 14.2239 12 14.5C12 14.7761 12.2239 15 12.5 15H14V16.5C14 16.7761 14.2239 17 14.5 17C14.7761 17 15 16.7761 15 16.5V15H16.5C16.7761 15 17 14.7761 17 14.5C17 14.2239 16.7761 14 16.5 14H15V12.5Z"
					/></g
				></svg
			>
			<p>Join or create a team</p>
		</footerleft>
		<footerright>
			<svg
				viewBox="-6 -6 32 32"
				class="app-svg icons-settings"
				focusable="false"
				role="presentation"
				><g class="icons-default-fill"
					><path
						class="icons-filled"
						d="M1.91099 7.38266C2.28028 6.24053 2.88863 5.19213 3.69133 4.30364C3.82707 4.15339 4.04002 4.09984 4.23069 4.16802L6.14897 4.85392C6.66905 5.03977 7.24131 4.76883 7.42716 4.24875C7.44544 4.19762 7.45952 4.14507 7.46925 4.09173L7.83471 2.08573C7.87104 1.88627 8.02422 1.7285 8.22251 1.6863C8.8027 1.5628 9.39758 1.5 10.0003 1.5C10.6026 1.5 11.1971 1.56273 11.7769 1.68607C11.9752 1.72824 12.1284 1.88591 12.1648 2.08529L12.5313 4.09165C12.6303 4.63497 13.1511 4.9951 13.6944 4.89601C13.7479 4.88627 13.8004 4.87219 13.8515 4.85395L15.7698 4.16802C15.9605 4.09984 16.1734 4.15339 16.3092 4.30364C17.1119 5.19213 17.7202 6.24053 18.0895 7.38266C18.1518 7.57534 18.0918 7.78658 17.9374 7.91764L16.3825 9.23773C15.9615 9.5952 15.9101 10.2263 16.2675 10.6473C16.3027 10.6887 16.3411 10.7271 16.3825 10.7623L17.9374 12.0824C18.0918 12.2134 18.1518 12.4247 18.0895 12.6173C17.7202 13.7595 17.1119 14.8079 16.3092 15.6964C16.1734 15.8466 15.9605 15.9002 15.7698 15.832L13.8515 15.1461C13.3315 14.9602 12.7592 15.2312 12.5733 15.7512C12.5551 15.8024 12.541 15.8549 12.5312 15.9085L12.1648 17.9147C12.1284 18.1141 11.9752 18.2718 11.7769 18.3139C11.1971 18.4373 10.6026 18.5 10.0003 18.5C9.39758 18.5 8.8027 18.4372 8.22251 18.3137C8.02422 18.2715 7.87104 18.1137 7.83471 17.9143L7.46926 15.9084C7.37018 15.365 6.8494 15.0049 6.30608 15.104C6.25265 15.1137 6.20011 15.1278 6.14906 15.1461L4.23069 15.832C4.04002 15.9002 3.82707 15.8466 3.69133 15.6964C2.88863 14.8079 2.28028 13.7595 1.91099 12.6173C1.84869 12.4247 1.90876 12.2134 2.06313 12.0824L3.61798 10.7623C4.03897 10.4048 4.09046 9.77373 3.73299 9.35274C3.69784 9.31135 3.65937 9.27288 3.618 9.23775L2.06313 7.91764C1.90876 7.78658 1.84869 7.57534 1.91099 7.38266ZM8.00026 10C8.00026 11.1046 8.89569 12 10.0003 12C11.1048 12 12.0003 11.1046 12.0003 10C12.0003 8.89543 11.1048 8 10.0003 8C8.89569 8 8.00026 8.89543 8.00026 10Z"
					/><path
						class="icons-unfilled"
						d="M1.91099 7.38266C2.28028 6.24053 2.88863 5.19213 3.69133 4.30364C3.82707 4.15339 4.04002 4.09984 4.23069 4.16802L6.14897 4.85392C6.66905 5.03977 7.24131 4.76883 7.42716 4.24875C7.44544 4.19762 7.45952 4.14507 7.46925 4.09173L7.83471 2.08573C7.87104 1.88627 8.02422 1.7285 8.22251 1.6863C8.8027 1.5628 9.39758 1.5 10.0003 1.5C10.6026 1.5 11.1971 1.56273 11.7769 1.68607C11.9752 1.72824 12.1284 1.88591 12.1648 2.08529L12.5313 4.09165C12.6303 4.63497 13.1511 4.9951 13.6944 4.89601C13.7479 4.88627 13.8004 4.87219 13.8515 4.85395L15.7698 4.16802C15.9605 4.09984 16.1734 4.15339 16.3092 4.30364C17.1119 5.19213 17.7202 6.24053 18.0895 7.38266C18.1518 7.57534 18.0918 7.78658 17.9374 7.91764L16.3825 9.23773C15.9615 9.5952 15.9101 10.2263 16.2675 10.6473C16.3027 10.6887 16.3411 10.7271 16.3825 10.7623L17.9374 12.0824C18.0918 12.2134 18.1518 12.4247 18.0895 12.6173C17.7202 13.7595 17.1119 14.8079 16.3092 15.6964C16.1734 15.8466 15.9605 15.9002 15.7698 15.832L13.8515 15.1461C13.3315 14.9602 12.7592 15.2312 12.5733 15.7512C12.5551 15.8024 12.541 15.8549 12.5312 15.9085L12.1648 17.9147C12.1284 18.1141 11.9752 18.2718 11.7769 18.3139C11.1971 18.4373 10.6026 18.5 10.0003 18.5C9.39758 18.5 8.8027 18.4372 8.22251 18.3137C8.02422 18.2715 7.87104 18.1137 7.83471 17.9143L7.46926 15.9084C7.37018 15.365 6.8494 15.0049 6.30608 15.104C6.25265 15.1137 6.20011 15.1278 6.14906 15.1461L4.23069 15.832C4.04002 15.9002 3.82707 15.8466 3.69133 15.6964C2.88863 14.8079 2.28028 13.7595 1.91099 12.6173C1.84869 12.4247 1.90876 12.2134 2.06313 12.0824L3.61798 10.7623C4.03897 10.4048 4.09046 9.77373 3.73299 9.35274C3.69784 9.31135 3.65937 9.27288 3.618 9.23775L2.06313 7.91764C1.90876 7.78658 1.84869 7.57534 1.91099 7.38266ZM2.97154 7.37709L4.26523 8.47546C4.34803 8.54576 4.42496 8.62269 4.49526 8.70548C5.2102 9.54746 5.10721 10.8096 4.26521 11.5246L2.97154 12.6229C3.26359 13.4051 3.68504 14.1322 4.21648 14.7751L5.81246 14.2044C5.91473 14.1679 6.01982 14.1397 6.12667 14.1202C7.21332 13.922 8.25487 14.6423 8.45305 15.729L8.75702 17.3975C9.16489 17.4655 9.58024 17.5 10.0003 17.5C10.42 17.5 10.8351 17.4656 11.2427 17.3976L11.5475 15.7289C11.567 15.6221 11.5951 15.517 11.6317 15.4147C12.0034 14.3746 13.1479 13.8327 14.1881 14.2044L15.784 14.7751C16.3155 14.1322 16.7369 13.4051 17.029 12.6229L15.7353 11.5245C15.6525 11.4542 15.5756 11.3773 15.5053 11.2945C14.7903 10.4525 14.8933 9.1904 15.7353 8.47544L17.029 7.37709C16.7369 6.59486 16.3155 5.86783 15.784 5.22494L14.1881 5.79559C14.0858 5.83214 13.9807 5.8603 13.8738 5.87979C12.7872 6.07796 11.7456 5.3577 11.5475 4.27119L11.2427 2.60235C10.8351 2.53443 10.42 2.5 10.0003 2.5C9.58024 2.5 9.16489 2.53448 8.75702 2.60249L8.45304 4.27105C8.43355 4.37791 8.40539 4.48299 8.36884 4.58527C7.99714 5.62542 6.8526 6.1673 5.81237 5.79556L4.21648 5.22494C3.68504 5.86783 3.26359 6.59486 2.97154 7.37709ZM7.50026 10C7.50026 8.61929 8.61954 7.5 10.0003 7.5C11.381 7.5 12.5003 8.61929 12.5003 10C12.5003 11.3807 11.381 12.5 10.0003 12.5C8.61954 12.5 7.50026 11.3807 7.50026 10ZM8.50026 10C8.50026 10.8284 9.17183 11.5 10.0003 11.5C10.8287 11.5 11.5003 10.8284 11.5003 10C11.5003 9.17157 10.8287 8.5 10.0003 8.5C9.17183 8.5 8.50026 9.17157 8.50026 10Z"
					/></g
				></svg
			>
		</footerright>
	</footer>
</mstteamselection>

<style>
	mstteamselection {
		background-color: #f0f0f0;
		width: 360px;
		height: 100%;
		box-shadow: inset;
	}

	mstteamselection header {
		height: 60px;
		display: flex;
		justify-content: space-between;
		border-bottom: 1.5px solid #e0e0e0;
	}

	mstteamselection header h2 {
		font-weight: 700;
		font-size: 18px;
		align-self: center;
		margin-left: 16px;
	}

	mstteamselection header svg {
		width: 40px;
		height: 40px;
		align-self: center;
		margin-right: 8px;
	}

	mstteamselection header svg .icons-unfilled {
		fill: #616161;
	}

	mstteamselection header svg .icons-filled {
		display: none;
	}

	teamlist {
		display: block;
		width: 100%;
		height: calc(100% - 60px - 55px);
	}

	teamlist ul {
		display: block;
		width: 100%;
		list-style: none;
		margin: 0;
		padding: 0;
	}

	footer {
		display: flex;
		justify-content: space-between;
		color: #616161;
		height: 55px;
		border-top: 1px solid #e0e0e0;
		margin-left: 16px;
		margin-right: 16px;
	}

	footer * {
		align-self: center;
	}

	footerleft {
		display: flex;
	}

	footerleft p {
		font-size: 14px;
		margin-left: 4px;
	}

	footerleft svg {
		fill: #616161;
		width: 30px;
	}

	footerleft svg .icons-filled {
		display: none;
	}

	footerleft:hover {
		color: var(--mspurple);
	}

	footerleft:hover svg .icons-unfilled {
		fill: var(--mspurple);
	}

	footerleft:hover svg .icons-filled {
		display: block;
		fill: var(--mspurple);
	}

	footerright svg {
		fill: #616161;
		width: 30px;
	}

	footerright svg .icons-filled {
		display: none;
	}

	footerright svg:hover .icons-unfilled {
		fill: var(--mspurple);
	}

	footerright svg:hover .icons-filled {
		display: block;
		fill: var(--mspurple);
	}

	@media (prefers-color-scheme: dark) {
		mstteamselection {
			background-color: #141414;
		}
		mstteamselection header {
			border-bottom: 1.5px solid #000;
		}

		mstteamselection header h2 {
			color: white;
		}

		mstteamselection header svg .icons-unfilled {
			fill: #adadad;
		}

		footer {
			border-top: 1px solid #000;
		}

		footerleft p {
			color: #adadad;
		}

		footerleft svg {
			fill: #adadad;
		}

		footerleft:hover p {
			color: var(--mspurpledarkmode);
		}

		footerleft:hover svg .icons-unfilled {
			fill: var(--mspurpledarkmode);
		}

		footerleft:hover svg .icons-filled {
			fill: var(--mspurpledarkmode);
		}

		footerright svg:hover .icons-unfilled {
			fill: var(--mspurpledarkmode);
		}

		footerright svg:hover .icons-filled {
			fill: var(--mspurpledarkmode);
		}

		footerright svg {
			fill: #adadad;
		}
	}
</style>

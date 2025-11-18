<script lang="ts" module>
	import CloudFlare from '$lib/assets/favicon.png';
	import Nikhil from '$lib/assets/avatars/nikhil.png';
	import AudioWaveformIcon from "@lucide/svelte/icons/audio-waveform";
	import HouseIcon from "@lucide/svelte/icons/house";
	import MessageSquareDotIcon from "@lucide/svelte/icons/message-square-dot";
	import SettingsIcon from "@lucide/svelte/icons/settings";
	import ChartPieIcon from "@lucide/svelte/icons/chart-pie";
	import CommandIcon from "@lucide/svelte/icons/command";
	import FrameIcon from "@lucide/svelte/icons/frame";
	import GalleryVerticalEndIcon from "@lucide/svelte/icons/gallery-vertical-end";
	import MapIcon from "@lucide/svelte/icons/map";
	import ClipBoardClockIcon from "@lucide/svelte/icons/clipboard-clock";
	import HistoryIcon from "@lucide/svelte/icons/history";
	import GiftIcon from "@lucide/svelte/icons/gift";
	import HelpIcon from "@lucide/svelte/icons/help-circle";

	// This is sample data.
	const data = {
		user: {
			name: "Nikhil Tirumalasetty",
			email: "nikhil@example.com",
			avatar: Nikhil,
		},
		teams: [
			{
				name: "Acme Inc",
				logo: GalleryVerticalEndIcon,
				plan: "Enterprise",
			},
			{
				name: "Acme Corp.",
				logo: AudioWaveformIcon,
				plan: "Startup",
			},
			{
				name: "Evil Corp.",
				logo: CommandIcon,
				plan: "Free",
			},
		],
		navMain: [
			{
				title: "Home",
				url: "#",
				icon: HouseIcon,
			},
			{
				title: "Recents",
				url: "#",
				icon: HistoryIcon,
				items: [
					{
						title: "Workers & Pages",
						url: "#",
					},
					{
						title: "Containers",
						url: "#",
					},
					{
						title: "Hyperdrive",
						url: "#",
					},
				],
			},
			{
				title: "Notifications",
				url: "#",
				icon: MessageSquareDotIcon,
			},
			{
				title: "Activity",
				url: "#",
				icon: ClipBoardClockIcon,
			},
		],
		pins: [
			{
				name: "Workers & Pages",
				url: "#",
				icon: FrameIcon,
			},
			{
				name: "thinkwithnikhil.com",
				url: "#",
				icon: ChartPieIcon,
			},
			{
				name: "Workers AI",
				url: "#",
				icon: MapIcon,
			},
		],
		navSecondary: [
			{
				title: "Settings",
				url: "#",
				icon: SettingsIcon,
			},
			{
				title: "What's New",
				url: "#",
				icon: GiftIcon,
			},
			{
				title: "Get Help",
				url: "#",
				icon: HelpIcon,
			},
		],
	};
</script>

<script lang="ts">
	import NavMain from "./nav-main.svelte";
	import NavPins from "./nav-pins.svelte";
	import NavUser from "./nav-user.svelte";
	import NavSecondary from './nav-secondary.svelte';
	import TeamSwitcher from "./team-switcher.svelte";
	import * as Sidebar from "$lib/components/ui/sidebar/index.js";
	import type { ComponentProps } from "svelte";

	let {
		ref = $bindable(null),
		collapsible = "icon",
		...restProps
	}: ComponentProps<typeof Sidebar.Root> = $props();
</script>

<Sidebar.Root {collapsible} {...restProps}>
	<Sidebar.Header>
		<Sidebar.Menu>
		<Sidebar.MenuItem>
			<Sidebar.MenuButton class="data-[slot=sidebar-menu-button]:p-1.5!">
			{#snippet child({ props })}
				<a href="##" {...props}>
				<img src={CloudFlare} alt="CloudFlare Logo" class="max-w-full h-6 rounded-md" />
				<span class="font-sans ml-2 text-xs font-semibold tracking-wider">CLOUDFLARE</span>
				</a>
			{/snippet}
			</Sidebar.MenuButton>
		</Sidebar.MenuItem>
		</Sidebar.Menu>
		<TeamSwitcher teams={data.teams} />
	</Sidebar.Header>
	<Sidebar.Content>
		<NavMain items={data.navMain} />
		<NavPins pins={data.pins} />
		<NavSecondary items={data.navSecondary} class="mt-auto" />
	</Sidebar.Content>
	<Sidebar.Footer>
		<NavUser user={data.user} />
	</Sidebar.Footer>
	<Sidebar.Rail />
</Sidebar.Root>

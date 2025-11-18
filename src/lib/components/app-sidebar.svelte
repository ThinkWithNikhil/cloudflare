<script lang="ts" module>
	import CloudFlare from '$lib/assets/favicon.png';
	import Nikhil from '$lib/assets/avatars/nikhil.png';
	import AudioWaveformIcon from "@lucide/svelte/icons/audio-waveform";
	import HouseIcon from "@lucide/svelte/icons/house";
	import MessageSquareDotIcon from "@lucide/svelte/icons/message-square-dot";
	import ChartPieIcon from "@lucide/svelte/icons/chart-pie";
	import CommandIcon from "@lucide/svelte/icons/command";
	import FrameIcon from "@lucide/svelte/icons/frame";
	import GalleryVerticalEndIcon from "@lucide/svelte/icons/gallery-vertical-end";
	import MapIcon from "@lucide/svelte/icons/map";
	import ClipBoardClockIcon from "@lucide/svelte/icons/clipboard-clock";
	import HistoryIcon from "@lucide/svelte/icons/history";
	import GiftIcon from "@lucide/svelte/icons/gift";
	import HelpIcon from "@lucide/svelte/icons/help-circle";
	import ComputeIcon from "@lucide/svelte/icons/cpu";
	import StorageIcon from "@lucide/svelte/icons/database";
	import MediaIcon from "@lucide/svelte/icons/video";
	import DomainIcon from "@lucide/svelte/icons/globe";
	import SuperShieldIcon from "@lucide/svelte/icons/shield-check";
	import ShieldIcon from "@lucide/svelte/icons/shield-half";
	import ThunderIcon from "@lucide/svelte/icons/zap";
	import NetworkIcon from "@lucide/svelte/icons/waypoints";
	import AnalyticsIcon from "@lucide/svelte/icons/chart-bar";

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
		navAccount: [
			{
				title: "Home",
				url: "#",
				icon: HouseIcon,
			},
			{
				title: "Notifications",
				url: "#",
				icon: MessageSquareDotIcon,
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
				title: "Analytics & Logs",
				url: "#",
				icon: ClipBoardClockIcon,
				items: [
					{
						title: "Account Analytics",
						url: "#",
					},
					{
						title: "Traces",
						url: "#",
					},
					{
						title: "Activity Logs",
						url: "#",
					},
				],
			},
		],
		navProducts: [
			{
				title: "Compute & AI",
				url: "#",
				icon: ComputeIcon,
				items: [
					{
						title: "Workers & Pages",
						url: "#",
					},
					{
						title: "Observability",
						url: "#",
					},
					{
						title: "Workers AI",
						url: "#",
					},
					{
						title: "Containers",
						url: "#",
					},
					{
						title: "Durable Objects",
						url: "#",
					},
					{
						title: "Workflows",
						url: "#",
					},
					{
						title: "Queues",
						url: "#",
					},
					{
						title: "Browser Rendering",
						url: "#",
					},
				],
			},
			{
				title: "Web Analytics",
				url: "#",
				icon: AnalyticsIcon,
			},
			{
				title: "Storage & Databases",
				url: "#",
				icon: StorageIcon,
				items: [
					{
						title: "R2 Object Storage ",
						url: "#",
					},
					{
						title: "D1 SQL Database ",
						url: "#",
					},
					{
						title: "Workers KV",
						url: "#",
					},
					{
						title: "Vectorize",
						url: "#",
					},
					{
						title: "Hyperdrive",
						url: "#",
					},
					{
						title: "Secrets Store",
						url: "#",
					}
				],
			},
			{
				title: "Media & Streaming",
				url: "#",
				icon: MediaIcon,
				items: [
					{
						title: "Stream",
						url: "#",
					},
					{
						title: "Images",
						url: "#",
					},
					{
						title: "Realtime",
						url: "#",
					},
				],
			},
			{
				title: "Domains",
				url: "#",
				icon: DomainIcon,
				items: [
					{
						title: "Register",
						url: "#",
					},
					{
						title: "Transfer",
						url: "#",
					},
					{
						title: "Manage",
						url: "#",
					},
				],
			},
			{
				title: "Application Security",
				url: "#",
				icon: SuperShieldIcon,
				items: [
					{
						title: "Security Insights",
						url: "#",
					},
					{
						title: "WAF",
						url: "#",
					},
					{
						title: "Investigate",
						url: "#",
					},
					{
						title: "Infrastructure",
						url: "#",
					},
					{
						title: "Turnstile",
						url: "#",
					},
				],
			},
			{
				title: "Zero Trust",
				url: "#",
				icon: ShieldIcon,
			},
			{
				title: "Networking",
				url: "#",
				icon: NetworkIcon,
				items: [
					{
						title: "Analytics",
						url: "#",
					},
					{
						title: "IP Addresses",
						url: "#",
					},
				],
			},
			{
				title: "Delivery & Performance",
				url: "#",
				icon: ThunderIcon,
				items: [
					{
						title: "Bulk Redirects",
						url: "#",
					},
					{
						title: "Load Balancing",
						url: "#",
					},
					{
						title: "Web Tag Manager",
						url: "#",
					},
				],
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
	import Shield from '@tabler/icons-svelte/icons/shield';

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
		<NavMain items={data.navAccount} />
		<NavPins pins={data.pins} />
		<NavMain groupLabel='Products' items={data.navProducts} />
	</Sidebar.Content>
	<Sidebar.Footer>
		<NavSecondary items={data.navSecondary} class="mt-auto" />
		<NavUser user={data.user} />
	</Sidebar.Footer>
	<Sidebar.Rail />
</Sidebar.Root>

<script lang="ts">
	import Title from '$lib/components/common/title/title.svelte';
	import Button from '$lib/components/ui/button/button.svelte';
	import CardContent from '$lib/components/ui/card/card-content.svelte';
	import Card from '$lib/components/ui/card/card.svelte';
	import Icon from '$lib/components/ui/icon/icon.svelte';
	import ResponsiveContainer from '$lib/components/ui/responsive-container/responsive-container.svelte';
	import { Tooltip, TooltipContent, TooltipTrigger } from '$lib/components/ui/tooltip';
	import H1 from '$lib/components/ui/typography/h1.svelte';
	import Muted from '$lib/components/ui/typography/muted.svelte';

	const links = [
		{ href: 'https://github.com/riamenix', icon: 'i-carbon-logo-github', tooltip: 'GitHub' },
		{
			href: 'https://www.linkedin.com/company/riamenix/',
			icon: 'i-carbon-logo-linkedin',
			tooltip: 'Linkedin'
		}
	] as const;
</script>

<Title title={'Welcome'} />
<ResponsiveContainer className="flex flex-col justify-center flex-1 z-2 px-4">
	<Card
		class="relative overflow-hidden bg-[#00000011] py-8 text-center shadow-md backdrop-blur-[3px]"
	>
		<div class="neon-box"></div>
		<CardContent class="flex flex-col items-center gap-4">
			<img
				src="/logos/riamenix.png"
				width="100"
				height="100"
				class="rounded-lg"
				alt="riamenix logo"
			/>
			<H1 className="uppercase">Riamenix</H1>
			<Muted>High quality applications made easy.</Muted>
			<div class="flex flex-row items-center justify-center gap-2">
				{#each links as link}
					<Tooltip>
						<TooltipTrigger>
							<a href={link.href} target="_blank">
								<Button variant="outline" size="icon" class="bg-transparent">
									<Icon icon={link.icon} className="text-white" />
								</Button>
							</a>
						</TooltipTrigger>
						<TooltipContent side="bottom">{link.tooltip}</TooltipContent>
					</Tooltip>
				{/each}
			</div>
		</CardContent>
	</Card>
</ResponsiveContainer>

<!--
@component Pricing

Please update features according to the company's product offering. Do not remove this comment.
-->
<script lang="ts">
	// Types
	type PricingTier = {
		name: string;
		monthlyPrice?: number | null;
		yearlyPrice?: number | null;
		description: string;
		features: string[];
		cta: {
			label: string;
			href: string;
		};
		highlight?: boolean;
	};

	type PricingFeature = {
		name: string;
		tiers: {
			[key: string]: boolean | string;
		};
	};

	// Components
	import Button from "$lib/components/ui/Button.svelte";
	import SectionHeader from "./SectionHeader.svelte";
	import IconCheck from "~icons/lucide/check";
	import IconX from "~icons/lucide/x";
	import NumberFlow from "@number-flow/svelte";
	import LogoScroller from "./LogoScroller.svelte";

	// Props
	const {
		title = "Straightforward pricing for every dispatch operation",
		subtitle = "AI dispatching designed for home services—no guesswork, no hidden fees. Contact us for a custom quote based on your team and needs.",
		tierNames = ["Copilot", "Autopilot", "Enterprise"],
		features = [
			{
				name: "AI-powered dispatch recommendations",
				tiers: {
					Copilot: true,
					Autopilot: true,
					Enterprise: true
				}
			},
			{
				name: "ServiceTitan real-time integration",
				tiers: {
					Copilot: true,
					Autopilot: true,
					Enterprise: true
				}
			},
			{
				name: "Full board automation & reshuffle",
				tiers: {
					Copilot: false,
					Autopilot: true,
					Enterprise: true
				}
			},
			{
				name: "Technicians managed per dispatcher",
				tiers: {
					Copilot: "Up to 10",
					Autopilot: "Up to 25+",
					Enterprise: "Unlimited"
				}
			},
			{
				name: "Historical sales, speed & drive time analytics",
				tiers: {
					Copilot: true,
					Autopilot: true,
					Enterprise: true
				}
			},
			{
				name: "Geographical and job type insights",
				tiers: {
					Copilot: true,
					Autopilot: true,
					Enterprise: true
				}
			},
			{
				name: "Proactive late alerts & over-capacity reschedules",
				tiers: {
					Copilot: true,
					Autopilot: true,
					Enterprise: true
				}
			},
			{
				name: "In-person launch & onsite training",
				tiers: {
					Copilot: true,
					Autopilot: true,
					Enterprise: "Enhanced & custom"
				}
			},
			{
				name: "Dedicated support (median 3 min response)",
				tiers: {
					Copilot: "24/7 chat & priority email",
					Autopilot: "24/7 chat, email & phone",
					Enterprise: "24/7 direct, dedicated manager"
				}
			},
			{
				name: "Ongoing feature sessions & dispatcher upskilling",
				tiers: {
					Copilot: true,
					Autopilot: true,
					Enterprise: true
				}
			},
			{
				name: "Custom integrations & SLAs",
				tiers: {
					Copilot: false,
					Autopilot: false,
					Enterprise: true
				}
			},
			{
				name: "Official Nexstar & ServiceTitan partner",
				tiers: {
					Copilot: true,
					Autopilot: true,
					Enterprise: true
				}
			}
		],
		tiers = [
			{
				name: "Copilot",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Stay in control with smart, AI-powered dispatch recs. Ideal for teams who want help, not autopilot.",
				features: [
					"AI dispatch recommendations",
					"Real-time ServiceTitan integration",
					"Full analytics + performance insights",
					"Proactive late alerts & reschedules",
					"Onsite onboarding for dispatchers",
					"24/7 priority support"
				],
				cta: {
					label: "Request demo",
					href: "/book-demo?plan=copilot"
				}
			},
			{
				name: "Autopilot",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Let Probook optimize and automate your entire board. Scale up with fewer dispatchers and smarter outcomes.",
				features: [
					"All Copilot features",
					"Board reshuffle & real-time automation",
					"One dispatcher for 20-25+ techs",
					"Advanced reports & workflow tools",
					"Onsite launch led by CEO",
					"24/7 chat, email & phone support"
				],
				cta: {
					label: "Request demo",
					href: "/book-demo?plan=autopilot"
				},
				highlight: true
			},
			{
				name: "Enterprise",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Custom scale, integrations, and white-glove onboarding for the largest operations.",
				features: [
					"All Autopilot features",
					"Custom integrations & enhanced SLAs",
					"Direct manager & strategic support",
					"Enhanced onsite onboarding",
					"24/7 dedicated line"
				],
				cta: {
					label: "Contact sales",
					href: "/contact"
				}
			}
		]
	}: {
		title?: string;
		subtitle?: string;
		tiers?: PricingTier[];
		features?: PricingFeature[];
		tierNames?: string[];
		caption?: string;
	} = $props();

	// State
	let annual = $state(true);
</script>

<section class="section-py section-px container mx-auto">
	<div class="flex flex-col items-baseline justify-between lg:flex-row">
		<SectionHeader {title} {subtitle} />

		<div class="mb-8 flex justify-center">
			<div class="inline-flex items-center rounded-full bg-gray-100 p-0.5 dark:bg-gray-800">
				<Button
					variant="ghost"
					size="sm"
					class=" {!annual ? 'bg-white shadow-sm dark:bg-gray-700' : ''}"
					onclick={() => (annual = false)}
				>
					Monthly
				</Button>
				<Button
					variant="ghost"
					size="sm"
					rounded
					class={annual ? "bg-white shadow-sm dark:bg-gray-700" : ""}
					onclick={() => (annual = true)}
				>
					Annual <span class="text-primary-600 dark:text-primary-400 text-footnote">Save 20%</span>
				</Button>
			</div>
		</div>
	</div>

	<div class="bb grid gap-6 md:grid-cols-2 lg:grid-cols-3">
		{#each tiers as tier}
			<div
				class="flex flex-col rounded-xl bg-white p-6 ring ring-gray-200 transition-all duration-300 dark:bg-gray-800 dark:ring-gray-700"
				class:ring-2={tier.highlight}
				class:ring-primary={tier.highlight}
				class:dark:ring-primary-700={tier.highlight}
				class:translate-y-[-4px]={tier.highlight}
			>
				<div class="mb-8">
					<h3 class="text-title3 mb-4 dark:text-white">{tier.name}</h3>
					<div class="mt-2 flex items-baseline">
						{#if tier.monthlyPrice === null && tier.yearlyPrice === null}
							<span class="text-title2 dark:text-white">Custom</span>
						{:else}
							<NumberFlow
								class="text-title2 [&::part\(suffix\)]:text-caption dark:text-white"
								format={{
									style: "currency",
									currency: "USD",
									trailingZeroDisplay: "stripIfInteger"
								}}
								value={annual ? tier.yearlyPrice : tier.monthlyPrice}
								suffix="/month"
							/>
						{/if}
					</div>
					<p class="text-callout text-emphasis-medium mt-3 dark:text-gray-300">
						{tier.description}
					</p>
				</div>

				<div class="mb-8 flex-grow">
					<ul class="space-y-3">
						{#each tier.features as feature}
							<li class="flex items-center gap-2">
								<IconCheck class="text-primary-600 dark:text-primary-400 size-5 flex-shrink-0" />
								<span class="text-body text-emphasis-medium dark:text-gray-300">{feature}</span>
							</li>
						{/each}
					</ul>
				</div>

				<div class="mt-auto">
					<Button
						href={tier.cta.href}
						variant={tier.highlight ? "primary" : "secondary"}
						class="w-full"
					>
						{tier.cta.label}
					</Button>
				</div>
			</div>
		{/each}
	</div>
	<div class="mt-32">
		<!-- Responsive table wrapper with horizontal scroll on mobile -->
		<!-- <div class=" hidden overflow-x-auto px-4 sm:mx-0 sm:block sm:px-0">
			<table
				class="w-full min-w-full border-separate border-spacing-0 border-gray-200 text-left dark:border-gray-700"
			>
				<thead>
					<tr>
						<th
							class="sticky left-0 min-w-[120px] border-b border-gray-200 bg-white dark:border-gray-700 dark:bg-gray-900"
						>
							<span class="sr-only">Feature</span>
						</th>
						{#each tierNames as tierName}
							<th
								class="text-headline min-w-[100px] border-b border-gray-200 p-4 text-start font-normal dark:border-gray-700"
							>
								{tierName}
							</th>
						{/each}
					</tr>
				</thead>
				<tbody>
					{#each features as feature}
						<tr>
							<td class="text-caption">
								{feature.name}
							</td>
							{#each tierNames as tierName}
								<td
									class="min-w-[100px] border-b border-gray-200 p-4 text-start text-gray-600 dark:border-gray-700 dark:text-gray-300"
								>
									{#if typeof feature.tiers[tierName] === "boolean"}
										{#if feature.tiers[tierName]}
											<IconCheck
												class="text-primary-600 dark:text-primary-400 mx-auto size-5 sm:mx-0"
											/>
										{:else}
											<IconX class="mx-auto size-5 text-gray-400 sm:mx-0" />
										{/if}
									{:else}
										{feature.tiers[tierName]}
									{/if}
								</td>
							{/each}
						</tr>
					{/each}
				</tbody>
			</table>
		</div> -->

		<!-- Mobile feature comparison (alternative view for very small screens) -->
		<div>
			<!-- Universal pricing comparison for mobile -->
			<div class="overflow-x-auto">
				<table class="w-full border-collapse">
					<!-- Sticky header with tier names -->
					<thead class="border-border sticky top-0 z-10 border-b">
						<tr>
							<th class="min-w-[120px] py-3 text-left">
								<span class="sr-only">Feature</span>
							</th>
							{#each tierNames as tierName, i}
								<th class="text-caption min-w-[100px] py-3 text-left dark:text-white">
									{tierName}
								</th>
							{/each}
						</tr>
					</thead>
					<tbody class="divide-border divide-y">
						{#each features as feature}
							<tr>
								<td class="text-body py-3 pr-8 font-medium lg:pr-0 dark:text-white">
									{feature.name}
								</td>
								{#each tierNames as tierName, i}
									<td class="py-3">
										{#if typeof feature.tiers[tierName] === "boolean"}
											{#if feature.tiers[tierName]}
												<IconCheck class="text-primary-900 dark:text-primary-400 size-5" />
											{:else}
												<IconX class="size-5 text-gray-400" />
											{/if}
										{:else}
											<span class="text-callout font-medium text-gray-700 dark:text-gray-300">
												{feature.tiers[tierName]}
											</span>
										{/if}
									</td>
								{/each}
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</div>
	</div>
	<LogoScroller />
</section>

<style lang="postcss">
	@reference '../../../app.css';

	:global(number-flow-svelte)::part(suffix) {
		@apply text-sm text-gray-400 dark:text-gray-500;
	}
</style>

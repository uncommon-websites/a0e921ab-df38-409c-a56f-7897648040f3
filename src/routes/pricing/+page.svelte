<script lang="ts">
	// Types
	import type { PageProps } from "./$types";

	// Components
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import Pricing from "$lib/components/layout/Pricing.svelte";

	// Props
	const { data }: PageProps = $props();
</script>

<Pricing />

<Testimonials
	testimonials={[
		{
			name: "Elena Morales",
			position: "Lead Dispatcher",
			company: "CoolBreeze HVAC",
			quote:
				"Probook paid for itself in under a month. I can handle more calls without feeling overwhelmed, and the AI makes confident dispatching so easy.",
			image:
				"/generated/image-a-latina-woman-dispatcher-in-an-hvac-off.webp"
		},
		{
			name: "Isaiah Carter",
			position: "Operations Manager",
			company: "Precision Plumbing Pros",
			quote:
				"We saw a real bump in booked jobs and less drive time. The value for the price is obvious–plus, setup was fast and support is always there when we need it.",
			image:
				"/generated/image-a-black-man-the-operations-manager-in-a-.webp"
		},
		{
			name: "Meredith Lane",
			position: "Owner",
			company: "Lane Electric Solutions",
			quote:
				"No wasted calls, bigger tickets. If you want to see true ROI on every tech in the field, you want Probook.",
			image:
				"/generated/image-a-white-woman-owner-of-an-electrical-ser.webp"
		}
	]}
/>

<CallToAction
  title="Dispatch smarter. Win the day."
  subtitle="See the impact right away—real results, real support."
  description="Probook AI recommends or automates every technician assignment—maximizing sales, minimizing drive time, and helping your dispatchers do more with less. Give your team confidence and see proven results with the only AI dispatch solution built by and for home service leaders."
  imageSrc="/generated/image-a-cheerful-technician-standing-in-a-bust.webp"
  callsToAction={[
    {
      href: '/book-demo',
      label: 'Book a demo',
      variant: 'primary'
    },
    {
      href: '/contact',
      label: 'Talk to sales',
      variant: 'secondary'
    }
  ]}
/>

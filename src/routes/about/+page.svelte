<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
  {
    title: "Built by dispatchers, for dispatchers",
    description: "We know the job because we’ve done it. Everything we build is rooted in real-world field experience and direct customer feedback."
  },
  {
    title: "Humble, practical, hands-on",
    description: "No big egos or tech hype. We work alongside our users and each other—solving real problems, iterating fast, and celebrating practical wins."
  },
  {
    title: "Tight feedback loops",
    description: "We move quickly by listening to dispatchers, techs, and managers every day. When there’s an issue, it gets fixed. When there’s a win, we share it."
  },
  {
    title: "Direct and honest",
    description: "Feedback is direct and communication is clear—inside our team and with customers. We do our best work when we help each other improve."
  }
];
</script>

<SecondaryHero
	title="Smarter dispatching, higher revenue"
	subtitle="Built by dispatchers, backed by real support"
	imageSrc="/mockups/airport-screen-1748545999798.png"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"We started in 2018 with a simple goal: make helpful tech that people actually need. While many chase profits, we chose to do things differently.",
		"Beyond making good products, we care about doing the right thing, being kind to our planet, and making sure everyone can use what we build. That's our compass.",
		"From day one, we've asked ourselves: 'Does this actually help people?' This question gets us through tough calls and shapes who we are. We're playing the long game here.",
		"We think about how our work affects real people's lives. We build tech that brings people together, keeps your information safe, and treats everyone fairly. When we stick to these basics, good things happen."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
	stakeholderType="team"
	title="Meet our founder."
	subtitle="In-person support and relentless focus on dispatchers."
	stakeholders={[
		{
			name: "George Eliadis",
			position: "Founder & CEO",
			bio: "George leads Probook AI with a commitment to hands-on support. He personally joins new teams during launch to help dispatchers build trust in AI and achieve real operational gains—fast. From board reshuffling to late alerts, George puts the needs of service businesses and their dispatchers first.",
			image: "/generated/image-a-professional-headshot-of-a-male-founde.webp"
		}
	]}
/>

<StakeholderGrid
	stakeholderType="investor"
	title="Backed by the best."
	subtitle="Point Nine, TSIC and others"
	stakeholders={[
		{
			name: "Point Nine Capital",
			image: "https://cdn.brandfetch.io/pointnine.com/w/400/h/400/logo?c=1id_elLz2Bd5Ej-dWo7"
		},
		{
			name: "TSIC Ventures",
			image: "https://cdn.brandfetch.io/tiny.vc/w/400/h/400/logo?c=1a2b3c4d5e"
		},
		{
			name: "Sequoia Capital",
			image: "https://cdn.brandfetch.io/sequoiacap.com/w/400/h/400/logo"
		}
	]}
/>

<!-- CTA Section -->
<CallToAction
  title="See Probook AI in action"
  subtitle="Book a demo with our team"
  description="Get hands-on with the only AI dispatch engine built by dispatchers, for dispatchers. See how we help the best companies increase sales, efficiency, and customer satisfaction—delivered with in-person support from real industry experts. Fast onboarding, instant value, and zero pressure."
  imageSrc="/generated/image-a-cheerful-home-services-dispatcher-and-.webp"
  callsToAction={[
    {
      href: "https://calendly.com/george-probook/demo",
      label: "Book a demo",
      variant: "primary"
    }
  ]}
/>

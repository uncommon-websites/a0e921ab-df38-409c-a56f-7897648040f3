<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CustomerCardHero from "$lib/components/layout/hero-sections/CustomerCardHero.svelte";
</script>

<CustomerCardHero
  centered={true}
  title="Smarter dispatching. Done for you."
  subtitle="Probook helps home services companies assign the right technician to every job—faster, easier, and more profitably."
  customers={[
    {
      name: "Dani Dascher",
      position: "Dispatcher, Auchinachie Services",
      imageSrc: "/generated/image-a-female-dispatcher-in-a-busy-call-cente.webp"
    },
    {
      name: "Mike Sullivan",
      position: "Lead Dispatcher, Auchinachie Services",
      imageSrc: "/generated/image-a-middle-aged-male-dispatcher-in-an-offi.webp"
    },
    {
      name: "Brandy Heesh",
      position: "Operations Manager, Auchinachie Services",
      imageSrc: "/generated/image-a-female-operations-manager-in-a-home-se.webp"
    },
    {
      name: "Chris Holleran",
      position: "General Manager, Auchinachie Services",
      imageSrc: "/generated/image-a-male-general-manager-of-an-hvac-compan.webp"
    },
    {
      name: "Ryan Laske",
      position: "Field supervisor & technician, TR Miller",
      imageSrc: "/generated/image-a-male-service-technician-in-a-branded-s.webp"
    }
  ]}
/>

<LogoScroller
	label="Trusted by industry leaders"
	logoUrls={[
		"https://logo.clearbit.com/onehourheatandair.com",
		"https://logo.clearbit.com/mrrooter.com",
		"https://logo.clearbit.com/aireserv.com"
	]}
/>

<Summary
	title="What we do"
	text="Probook AI is an AI-powered dispatching solution for home services companies. Assign the right technician to every job, boost sales and efficiency, and deliver better customer service—all without guesswork."
/>

<Testimonials
	testimonials={[
		{
			name: "Martina Rivas",
			position: "Dispatcher, Blake Brothers Plumbing",
			company: "Blake Brothers Plumbing",
			quote:
				"Probook saves me at least two hours every day. I finally get time to help customers and train new dispatchers instead of just fighting the board.",
			image: "/generated/image-a-female-dispatcher-in-a-lively-home-ser.webp"
		},
		{
			name: "Brett Stein",
			position: "Operations Manager, Lion Home Service",
			company: "Lion Home Service",
			quote:
				"We stopped missing critical jobs because the AI picked up things humans miss. That means less risk of an unhappy customer or lost revenue.",
			image: "/generated/image-a-male-operations-manager-in-a-bustling-.webp"
		},
		{
			name: "Malik Reed",
			position: "Owner, TR Miller Heating & Cooling",
			company: "TR Miller Heating & Cooling",
			quote:
				"Probook boosted our weekly sales by simply getting the right techs to the right calls. It paid for itself within days.",
			image: "/generated/image-a-male-business-owner-in-a-plumbing-comp.webp"
		}
	]}
/>

<Features
  title="Features that set Probook apart"
  subtitle="Why leading home service companies trust us"
  features={[
    {
      title: "AI-powered technician dispatch",
      description:
        "Assign the right tech to the right job in seconds, maximizing ticket value and efficiency every day."
    },
    {
      title: "Copilot and Autopilot modes",
      description:
        "Get real-time board recommendations or let Probook fully optimize your schedule—your dispatcher stays in control."
    },
    {
      title: "Instant ServiceTitan integration",
      description:
        "Live sync ensures your board, jobs, and customer data are always up to date, with no double entry."
    },
    {
      title: "Performance insights by tech and territory",
      description:
        "See metrics for sales, flip rates, driving time, and job types broken down by technician and zip code."
    },
    {
      title: "In-person launch and onboarding",
      description:
        "Your team gets hands-on setup, with our CEO personally supporting your dispatchers for a seamless start."
    },
    {
      title: "Lightning-fast support",
      description:
        "Enjoy a three minute median response, 25 minutes to resolution, and a 100% post-resolution satisfaction rate."
    }
  ]}
/>

<UseCases
  title="Use Cases"
  subtitle="Real-world applications for your business needs"
  useCases={[
    {
      title: "Maximize revenue from every call",
      description: "Let AI match high-value jobs with your top-performing techs based on historical sales and real profitability—not guesswork.",
      image: "/generated/image-a-group-of-technicians-preparing-to-leav.webp",
      link: {
        href: "/use-cases/maximize-revenue-per-call",
        label: "Learn more"
      }
    },
    {
      title: "Handle urgent requests without chaos",
      description: "Keep calm under pressure—your dispatcher gets instant, data-driven recommendations when emergencies hit and the board is packed.",
      image: "/generated/image-in-an-efficient-office-environment-a-dis.webp",
      link: {
        href: "/use-cases/manage-urgent-calls",
        label: "Learn more"
      }
    },
    {
      title: "Make every dispatcher a superstar",
      description: "With built-in coaching and automated best practices, even new hires confidently schedule smarter and boost tech productivity from day one.",
      image: "/generated/image-a-team-of-home-service-technicians-is-se.webp",
      link: {
        href: "/use-cases/dispatcher-success",
        label: "Learn more"
      }
    }
  ]}
/>

<AboutTeaser />
<CallToAction
  title="Better dispatching, without the guesswork"
  subtitle="Book a demo — see why the best home service companies rely on Probook"
  description="Probook AI helps home services businesses send the right tech to the right job—automatically. Boost revenue, save dispatcher time, and keep customers happy. Onboard in two days and get ongoing concierge support."
  imageSrc="/generated/image-a-happy-female-dispatcher-sitting-at-her.webp"
  callsToAction={[
    { href: "/book-demo", label: "Book a demo", variant: "primary" },
    { href: "/contact", label: "Contact sales", variant: "secondary" }
  ]}
/>

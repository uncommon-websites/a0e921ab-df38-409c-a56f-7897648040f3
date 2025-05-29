<script lang="ts">
	// Components
	import Summary from "$lib/components/layout/Summary.svelte";

	let {
	paragraphs = [
		"Probook AI started with a simple question: why is dispatch still the most stressful part of home service operations? After working closely with dispatchers, we saw the constant juggling—assigning the right tech, dealing with last-minute changes, and balancing sales with service—while relying on gut instinct and endless spreadsheets.",
		"We built Probook AI together with dispatchers and owners to solve this. Our team combined hands-on experience with smart automation, building the first AI-powered system that recommends or even fully automates tech assignments. It connects in real time to ServiceTitan, adapts to your team’s needs, and always keeps humans in charge when it matters. We don’t just launch online—our CEO flies out in person to support new teams on day one.",
		"Today, Probook AI is trusted by some of the best in the business, helping teams work smarter, sell more, and delight customers. We’re committed to making dispatching easy, accurate, and a real driver of growth for every home service company."
	]
}: {
	paragraphs: string[];
} = $props();
</script>

<div class="">
	<article class="section-py container mx-auto grid max-w-full">
		<Summary text={paragraphs.join("\n\n")} />
	</article>
</div>

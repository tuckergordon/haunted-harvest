<script>
	import InfoPane from "./InfoPane.svelte";
	import Countdown from "./scroller/Countdown.svelte";
	import ImageScroller from "./scroller/ImageScroller.svelte";
	import ScrollerCard from "./scroller/ScrollerCard.svelte";

	const partyDate = new Date("2021-10-23T20:30:00Z");
</script>

<ImageScroller>
	<div slot="backdrop" style="position: relative">
		<img
			src="assets/images/woman-with-pumpkin.jpg"
			alt="woman-holding-pumpkin"
			style="width: 100%; height: 100%;"
		/>
		<Countdown
			style="position: absolute; top: 53%; left: 50%; transform: translate(-50%, -50%); font-size: 65px"
			date={partyDate}
		/>
	</div>
	<svelte:fragment slot="overlays">
		<div class="position: relative">
			<h2
				style="position: absolute; bottom: 50px; left: 50%; transform: translate(-50%, -50%); font-size: 36px; color: #fff"
			>
				Scroll down for more info...
			</h2>
		</div>
		<!-- spacer div -->
		<div style="min-height: 50vh" />
		<div>
			<ScrollerCard>Hey friend, it's been a minute</ScrollerCard>
		</div>
		<div>
			<ScrollerCard
				>We want to hang out with you on <span class="highlight"
					>Saturday night</span
				></ScrollerCard
			>
		</div>
		<div>
			<ScrollerCard
				>And by <span class="highlight">we</span>, we're talking Danny, Kate,
				Kenny, and Josie</ScrollerCard
			>
		</div>
		<div>
			<ScrollerCard
				>...and Tucker.<br />He doesn't live with us but he did make this silly
				website &#128522;</ScrollerCard
			>
		</div>
		<div>
			<ScrollerCard
				>Join us at <span class="highlight">700pm</span> for some pumpkin carving!</ScrollerCard
			>
		</div>
		<div>
			<ScrollerCard
				>Or just at <span class="highlight">830pm</span> for some indoor party time!</ScrollerCard
			>
		</div>
		<div>
			<ScrollerCard
				>You may be wondering<br /><span
					class="highlight"
					style="font-style: italic">does this party have a theme?</span
				></ScrollerCard
			>
		</div>
		<div>
			<ScrollerCard
				>Oh you can bet your sweet &#x1f383; it does!<br />Please join us for...</ScrollerCard
			>
		</div>
	</svelte:fragment>
</ImageScroller>
<InfoPane />

<style>
	.highlight {
		color: #ff8f00;
	}
</style>

<script>
	import Header from "../components/ui-components/Header.svelte";
	import MeetupItem from "../components/meetup-components/MeetupItem.svelte";

	const meetups = [
		{
			id: "m1",
			title: "Coding Bootcamp",
			subtitle: "Learn how to code in 2 hours.",
			description: "In this meetup, we will have some experts that will walk you through the basics of programming.",
			imageUrl: "https://images.unsplash.com/photo-1580927752452-89d86da3fa0a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80",
			address: "123 No Hacker St, Los Angeles, CA 90041",
			contactEmail: "code4hacks@test.com"
		},
		{
			id: "m2",
			title: "Swim Camp",
			subtitle: 'Let\s swim together.',
			description: "Meets every other day.",
			imageUrl: "https://images.unsplash.com/photo-1600965962102-9d260a71890d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
			address: "345 Swim Ct, Los Angeles, CA 90042",
			contactEmail: "swims@test.com"
		}
	]
</script>

<style>
	#meetups {
		margin-top: 5rem;
	}

</style>

<Header></Header>

<section id="meetups">
	{#each meetups as meetup}
		<MeetupItem></MeetupItem>
	{/each}
</section>


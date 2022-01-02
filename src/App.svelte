<script>
	import Header from "../components/ui-components/Header.svelte";
	import MeetupGrid from "../components/meetup-components/MeetupGrid.svelte";
	import TextInput from "../components/ui-components/TextInput.svelte";
	import Button from "../components/ui-components/Button.svelte";

	export let title = "";
    export let subtitle = "";
    export let imageURL = "";
    export let description = "";
    export let address = "";
    export let contactEmail = "";

	let meetups = [
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

	function addMeetup() {
		const newMeetup = {
			id: Math.random().toString(),
			title: title,
			subtitle: subtitle,
			description: description,
			imageUrl: imageURL,
			address: address,
			contactEmail: contactEmail
		}

		meetups = [newMeetup, ...meetups];	
	}
</script>

<style>
	main {
		margin-top: 6rem;
	}

	form {
		width: 30 rem;
		max-width: 90%;
		margin: auto
	}
</style>

<Header></Header>

<main>
	<form on:submit|preventDefault="{addMeetup}">
		<TextInput id="title" label="Title" type="text" rows="0" controlType="None" value={title} on:input="{(event) => title = event.target.value}"></TextInput>
		<TextInput id="subtitle" label="Subtitle" type="text" rows="0" controlType="None" value={subtitle} on:input="{(event) => subtitle = event.target.value}"></TextInput>
		<TextInput id="address" label="Address" type="text" rows="0" controlType="None" value={address} on:input="{(event) => address = event.target.value}"></TextInput>
		<TextInput id="imageURL" label="Image URL" type="text" rows="0" controlType="None" value={imageURL} on:input="{(event) => imageURL = event.target.value}"></TextInput>
		<TextInput id="contactEmail" label="E-mail" type="email" rows="0" controlType="None" value={contactEmail} on:input="{(event) => contactEmail = event.target.value}"></TextInput>
		<TextInput id="description" label="Description" type="text" rows="3" controlType="textarea" value={description} on:input="{(event) => description = event.target.value}"></TextInput>
		<Button type="submit" caption="Save"/>
	</form>
	<MeetupGrid {meetups}></MeetupGrid>
</main>


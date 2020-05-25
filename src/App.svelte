<script>
    import Header from "./UI/Header.svelte";
    import MeetupGrid from "./workshops/MeetupGrid.svelte";
    import TextInput from "./UI/TextInput.svelte";
    let title ='';
    let subtitle ='';
    let address ='';
    let imgUrl ='';
    let description ='';
    let meetups =[];

    let email = 'world';
    const Meetups = [
        {
            id: "m1",
            title: "Workshop svelte",
            subtitle: "learn svelte",
            description: "let's go",
            imgUrl: "https://s.s-bol.com/imgbase0/imagebase3/large/FC/6/5/2/3/9200000112933256.jpg",
            address: "@steve",
            contactEmail: "code@test.com"
        },
        {
            id: "m2",
            title: "Sicco's bday",
            subtitle: "whoop whop",
            description: "danse danse danse",
            imgUrl: "https://s.s-bol.com/imgbase0/imagebase3/large/FC/6/5/2/3/9200000112933256.jpg",
            address: "@sicco",
            contactEmail: "code@sicco.com"
        },
    ]

    function addMeetUp() {
        const newMeetUp ={
            id: Math.random().toString(),
            title: title,
            subtitle: subtitle,
            description: description,
            contactEmail: email,
            imgUrl: imgUrl,
            address: address

        };
       const meetups = [newMeetUp, ...Meetups];
    }
</script>
<style>
    #meetup {
        margin-top: 4rem;
    }
</style>
<Header/>
<section id="meetup">
    <MeetupGrid Meetups="{meetups}"/>
</section>
<main>
<form on:submit|preventDefault="{addMeetUp}" action="">
    <TextInput
    id="title"
    label="title"
    type="text"
    value="{title}"
    on:input={e => (title = e.target.value)}
    />
    <TextInput
            id="subtitle"
            label="subtitle"
            type="text"
            value="{subtitle}"
            on:input={e => (subtitle = e.target.value)}
    />
    <TextInput
            id="address"
            label="address"
            type="text"
            value="{address}"
            on:input={e => (address = e.target.value)}
    />
    <TextInput
            id="imgUrl"
            label="imgUrl"
            type="text"
            value="{imgUrl}"
            on:input={e => (imgUrl = e.target.value)}
    />
    <TextInput
            id="email"
            label="email"
            type="text"
            value="{email}"
            on:input={e => (email = e.target.value)}
    />
    <TextInput
            id="description"
            label="description"
            controlType="textarea"
            value="{description}"
            on:input={e => (description = e.target.value)}
    />
    <button type="submit">save</button>
</form>
</main>



<script>
    import MeetupItem from "./MeetupItem.svelte";
    export let Meetups;
</script>
<style>
    .section {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 1rem;
    }

    @media (min-width: 768px) {
        .section {
            grid-template-columns: repeat(2, 1fr);
        }
    }
</style>

<section class="section">
    {#each Meetups as Meetup, i(Meetup.id)}

        <MeetupItem
                title={Meetup.title}
                imgUrl={Meetup.imgUrl}
                subtitle={Meetup.subtitle}
                description={Meetup.description}
                address={Meetup.address}
                email={Meetup.contactEmail}
        />

    {/each}
</section>

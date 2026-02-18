<script lang="ts">
import { Card, Heading } from "flowbite-svelte";

const { eventIds, imgUrl } = $props();
</script>

<div class="flex flex-row flex-wrap">
{#each eventIds as eventId}
    <Card href="/event/{eventId}" img={eventId % 2 == 0 ? imgUrl : undefined} horizontal class="m-4 transition hover:shadow-xl" imgClass="max-w-40">
    <div class="m-4 flex flex-col gap-2">
        <Heading tag="h4">Event title</Heading>
        <p>A quick description of what will happen at this event</p>
        <span class="text-secondary-900 mt-auto">Mar. 1st | 10am - 3pm</span>
    </div>
    </Card>
{/each}
</div>

<script lang="ts">
import { Alert, Card, Heading, Button } from "flowbite-svelte";
import { CalendarMonthOutline, MapPinAltOutline, InfoCircleSolid } from "flowbite-svelte-icons";
import { page } from "$app/state";
import sampleEvent from "./sampleEvent.json";

const event = $state(sampleEvent);

let signedUp = $state(Number(page.params.id) > 4 ? false : true);
const toggleSignup = () => signedUp = !signedUp;
</script>

{#if event.past}
<Alert border class="m-4 flex flex-row">
    <InfoCircleSolid class="h-5 w-5" />
    <span class="font-bold">Note:</span>
    This event has already passed
</Alert>
{/if}

<div class="m-4 flex flex-row gap-4">
    <img src="https://flowbite-svelte.com/images/image-1.webp" alt="placeholder" class="w-full flex-1 rounded-md shadow-md" />
    <div class="flex-1 m-4 flex flex-col gap-8">
        <Heading tag="h2">{event.title}</Heading>
        <p>
            {event.description}
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </p>
        <Card class="p-4 text-secondary-900 flex flex-row gap-4"><CalendarMonthOutline class="shrink-0 h-6 w-6" /> {event.date} | {event.time}</Card>
        <Card class="p-4 text-secondary-900 flex flex-row gap-4"><MapPinAltOutline class="shrink-0 h-6 w-6" /> {event.location}</Card>
        {#if signedUp}
        <Button class="bg-dark-red hover:bg-red hover:cursor-pointer" onclick={toggleSignup}>I am no longer able to attend this event</Button>
        {:else}
        <Button class="bg-secondary-900 hover:cursor-pointer" onclick={toggleSignup}>I will be attending this event</Button>
        {/if}
    </div>
</div>

<script lang="ts">
import { Card, Heading } from "flowbite-svelte";
import { CalendarMonthOutline, MapPinAltOutline } from "flowbite-svelte-icons";

const event = $state({ title: "Event title", description: "A quick description of what will happen at this event", location: "1234 Market St., Philadelphia, PA 19104", date: "Mar. 1st", time: "10am - 3pm" });
</script>

<main class="max-w-[1280px] mx-auto">
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
        </div>
    </div>
</main>

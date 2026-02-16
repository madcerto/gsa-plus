<script lang="ts">
import { Heading, Hr } from "flowbite-svelte";
import Header from "./Header.svelte";
import PointsOverview from "./PointsOverview.svelte";
import EventList from "./EventList.svelte";

let user = $state({ fullName: "Juan Doe", stats: { points: 42, hours: 7 }, avatarImgUrl: "https://flowbite-svelte.com/images/profile-picture-3.webp" });
let registeredEventIds = $state([0, 1, 2, 3, 4]);
let upcomingEventIds = $state([5, 6, 7, 8, 9, 10, 11]);
</script>


<main class="max-w-[1280px] mx-auto">
    <div id="greeting" class="m-4">
        <Heading tag="h2">Welcome back, {user.fullName}</Heading>
        <Heading tag="h4" class="font-normal">Time to get involved in GSA!</Heading>
    </div>

    <PointsOverview points={user.stats.points} hours={user.stats.hours} />

    <Hr />

    <Heading tag="h2" class="m-4">Your events:</Heading>
    <EventList eventIds={registeredEventIds} imgUrl="https://flowbite-svelte.com/images/image-1.webp" />

    <Hr />

    <Heading tag="h2" class="m-4">Explore upcoming events:</Heading>
    <EventList eventIds={upcomingEventIds} imgUrl="https://flowbite.s3.amazonaws.com/docs/gallery/square/image-10.jpg" />
</main>

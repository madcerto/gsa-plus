<script lang="ts">
import { Heading, Hr } from "flowbite-svelte";
import PointsOverview from "./PointsOverview.svelte";
import EventList from "./EventList.svelte";
import sampleUser from "./sampleUser.json";

let user = $state(sampleUser);
let registeredEventIds = $state([0, 1, 2, 3, 4]);
let upcomingEventIds = $state([5, 6, 7, 8, 9, 10, 11]);
</script>

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

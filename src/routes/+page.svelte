<script lang="ts">
import { Heading } from "flowbite-svelte";
import Header from "./Header.svelte";
import PointsOverview from "./PointsOverview.svelte";

let user = $state({ fullName: "Juan Doe", stats: { points: 42, hours: 7 }, avatarImgUrl: "https://flowbite-svelte.com/images/profile-picture-3.webp" });
</script>

<Header {user} />

<main class="max-w-[1280px] mx-auto">
    <div id="greeting" class="m-4">
        <Heading tag="h2">Welcome back, {user.fullName}</Heading>
        <Heading tag="h4" class="font-normal">Time to get involved in GSA!</Heading>
    </div>

    <PointsOverview points={user.stats.points} hours={user.stats.hours} />
</main>

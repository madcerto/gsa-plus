<script lang="ts">
import { Heading } from "flowbite-svelte";

let user = $state({ fullName: "Juan Doe" });
</script>

<main class="max-w-[1280px] mx-auto">
    <div id="greeting" class="m-4">
        <Heading tag="h2">Welcome back, {user.fullName}</Heading>
        <Heading tag="h4" class="font-normal">Time to get involved in GSA!</Heading>
    </div>
</main>

<script lang="ts">
import { Heading, Label, Input, Button } from "flowbite-svelte";
import sampleEvent from "../sampleEvent.json";

const { form } = $props();
const event = $state(sampleEvent);
</script>

<Heading tag="h2" class="m-4">{event.title}</Heading>
<form method="post" class="m-4">
    <Label class="text-lg mb-2">Record attendance (swipe card or enter 8-digit Drexel ID):</Label>
    <div class="flex flex-row gap-4">
        <Input class="max-w-lg" />
        <Button>Go</Button>
    </div>
    {#if form?.success}<p class="text-green-600">Successfully recorded attendance</p>{/if}
    <input type="submit" hidden />
</form>

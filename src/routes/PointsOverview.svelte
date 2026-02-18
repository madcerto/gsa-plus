<script lang="ts">
import { Card, Button } from "flowbite-svelte";
import { AwardOutline, ClockOutline } from "flowbite-svelte-icons";

const { points, hours } = $props();
</script>

<Card size="lg" class="p-4 mx-4 gap-4">
    <div class="flex justify-between">
        <div class="flex flex-row">
            <AwardOutline class="h-full w-fit" />
            <div class="text-lg">
                Points:
                <p class="text-5xl font-bold">{points}</p>
            </div>
        </div>
        <span class="flex flex-row gap-1"><ClockOutline class="shrink-0 h-6 w-6" /> Hours: {hours}</span>
    </div>
    <Button class="w-fit self-end" href="/rewards">Redeem Rewards</Button>
</Card>

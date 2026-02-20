<script lang="ts">
import { Heading, Badge, Button, Modal } from "flowbite-svelte";
import RewardCard from "./RewardCard.svelte";
import sampleUser from "../sampleUser.json";

let userPoints = $state(sampleUser.stats.points);
let redeeming = $state(false);
let rewardCode: string | null = $state(null);

const handleRedeem = () => {
    userPoints -= 50;
    rewardCode = "ABCD1234!@#$";
}

$effect(() => { if (!redeeming) rewardCode = null; })
</script>

<div class="flex flex-row gap-4 m-4">
    <Heading tag="h2">Redeem rewards</Heading>
    <Badge class="text-2xl gap-2" color="secondary">Your points: <b>{userPoints}</b></Badge>
</div>

<div class="flex flex-row flex-wrap gap-4 m-4">
    <RewardCard {userPoints} title="$5 Digital Gift Card" requiredPoints={50} bind:redeeming={redeeming} />
    <RewardCard {userPoints} title="$15 Digital Gift Card" requiredPoints={150} bind:redeeming={redeeming} />
    <RewardCard {userPoints} bind:redeeming={redeeming} />
    <RewardCard {userPoints} title="$30 Digital Gift Card" requiredPoints={300} bind:redeeming={redeeming} />
    <RewardCard {userPoints} title="$50 Digital Gift Card" requiredPoints={500} bind:redeeming={redeeming} />
    <RewardCard {userPoints} title="$100 Digital Gift Card" requiredPoints={1000} bind:redeeming={redeeming} />
</div>

<Modal title="Redeem reward?" bind:open={redeeming}>
    {#if rewardCode}
    <Badge class="w-full text-md py-2.5">{rewardCode}</Badge>
    {:else}
    <Button class="w-full" onclick={handleRedeem}>Show Reward Code</Button>
    {/if}
    <p class="text-sm">Note: Be prepared to copy and save your reward code. It will not be shown again, and this action is irreversible.</p>
</Modal>

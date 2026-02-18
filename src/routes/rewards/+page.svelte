<script lang="ts">
import { Heading, Badge } from "flowbite-svelte";
import RewardCard from "./RewardCard.svelte";
import sampleUser from "../sampleUser.json";
</script>

<div class="flex flex-row gap-4 my-4">
    <Heading tag="h2">Redeem rewards</Heading>
    <Badge class="text-2xl gap-2" color="secondary">Your points: <b>{sampleUser.stats.points}</b></Badge>
</div>

<div class="flex flex-row flex-wrap gap-4">
    <RewardCard userPoints={sampleUser.stats.points} title="$5 Digital Gift Card" requiredPoints={50}/>
    <RewardCard userPoints={sampleUser.stats.points} title="$15 Digital Gift Card" requiredPoints={150}/>
    <RewardCard userPoints={sampleUser.stats.points}/>
    <RewardCard userPoints={sampleUser.stats.points} title="$30 Digital Gift Card" requiredPoints={300}/>
    <RewardCard userPoints={sampleUser.stats.points} title="$50 Digital Gift Card" requiredPoints={500}/>
    <RewardCard userPoints={sampleUser.stats.points} title="$100 Digital Gift Card" requiredPoints={1000}/>
</div>

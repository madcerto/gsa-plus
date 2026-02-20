<script lang="ts">
import { Badge, Button, Card } from "flowbite-svelte";

const {
    title = "$25 Digital Gift Card",
    description = "Pita Chip Gift Card",
    image = "https://static.wixstatic.com/media/a7f4a4_81c1fe2b18b546fd98dd080c6b922782~mv2.png/v1/fill/w_184,h_216,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/a7f4a4_81c1fe2b18b546fd98dd080c6b922782~mv2.png",
    requiredPoints = 250,
    userPoints
} = $props();

const canRedeem = $derived(userPoints >= requiredPoints);

function handleRedeem() {
    if (canRedeem) {
        alert("Reward redeemed!");
    }
}
</script>

<Card class="max-w-sm transition hover:shadow-xl"
    img={image}
    imgClass="rounded-t-lg h-48 w-full object-contain">
   <!-- Content -->
  <div class="p-5 space-y-4">
    <div class="flex justify-between items-start">
      <div>
        <h5 class="text-xl font-semibold">
          {title}
        </h5>
        <p class="text-sm text-gray-500">
          {description}
        </p>
      </div>

      <Badge color={canRedeem ? "green" : "red"}>
        {userPoints} / {requiredPoints} pts
      </Badge>
    </div>

    <!-- Progress / Points Info -->
    <div class="w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700">
        <div
          class="h-2.5 rounded-full bg-secondary-600 transition-all"
          style="width: {Math.min((userPoints / requiredPoints) * 100, 100)}%"
        ></div>
    </div>

    <!-- Redeem Button -->
    <Button
      color={canRedeem ? "primary" : "gray"}
      disabled={!canRedeem}
      class="w-full"
      onclick={handleRedeem}
    >
      {canRedeem ? "Redeem Reward" : "Not Enough Points"}
    </Button>
  </div>
</Card>

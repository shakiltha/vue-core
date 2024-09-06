<script setup>
defineProps({
  item: Object,
});
</script>

<template>
  <div class="my-2">
    <img :src="item.thumbnail" :alt="item.title" />
    <p class="font-bold text-2xl my-2">
      Title<span class="font-normal">{{ item.title }}</span>
    </p>
    <p class="font-bold text-xl my-2">
      Discount Percentage:
      <span class="font-normal">{{ item.discountPercentage }}</span>
    </p>
    <p class="font-bold text-xl my-2">
      Discount Total:
      <span class="font-normal">{{ item.discountedTotal }}</span>
    </p>
    <p class="font-bold text-xl my-2">
      Price: <span class="font-normal">{{ item.price }}</span>
    </p>
    <p class="font-bold text-xl my-2">
      Quantity: <span class="font-normal">{{ item.quantity }}</span>
    </p>
    <p class="font-bold text-xl my-2">
      Total: <span class="font-normal">{{ item.total }}</span>
    </p>
  </div>
</template>

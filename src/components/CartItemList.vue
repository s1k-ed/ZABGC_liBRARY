<script setup>
import { inject } from 'vue'
import CartItem from './CartItem.vue'

const { bookCartItems, addToCart } = inject('drawer')
</script>

<template>
  <div class="flex flex-col flex-1 gap-4 justify-between" v-auto-animate>
    <CartItem
      v-for="item in bookCartItems"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :author="item.author"
      :image-url="item.imageUrl"
      @on-click-remove="() => addToCart(item)"
    />
  </div>
</template>

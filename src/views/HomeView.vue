<script setup>
import CartComponent from '@/components/CartComponent.vue';
import HeroBanner from '@/components/HeroBanner.vue';
import FeaturedComponent from '@/components/FeaturedComponent.vue';
import BooksListing from '@/components/BooksListing.vue';

import { useBooksStore } from '@/stores/books';
import { useCartStore } from '@/stores/cart';
const booksStore = useBooksStore();
const cartStore = useCartStore();
</script>

<template>
  <cart-component
    v-if="cartStore.showCart"
    :cart="cartStore.cart"
    @hide-cart="cartStore.showCart = false"
    @increment-book="cartStore.incrementBookToCart"
    @decrement-book="cartStore.decrementBookToCart"
  />
  <template v-else>
    <hero-banner />
    <featured-component />
    <books-listing
      :books="booksStore.books"
      @add-to-cart="cartStore.addToCart"
    />
  </template>
</template>
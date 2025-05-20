<template>
     <section class="featured">
      <div>
        <span class="mdi mdi-truck"></span>
        <h2>Frete grátis para SC</h2>
      </div>
      <div>
        <span class="mdi mdi-star"></span>
        <h2>Livros recomendados</h2>
      </div>
      <div>
        <span class="mdi mdi-book-open-page-variant"></span>
        <h2>Mais vendidos</h2>
      </div>
    </section>
    <section class="books">
      <article class="book" v-for="book in books" :key="book.id">
        <img :src="book.cover" :alt="book.title" />
        <h2>{{ book.title }}</h2>
        <p class="book-author">{{ book.author }}</p>
        <span class="price-and-like">
          <p class="book-price">R$ {{ book.price.toFixed(2) }}</p>
          <span class="mdi mdi-heart-outline"></span>
        </span>
        <button @click="addToCart(book)">
          <span class="mdi mdi-cart"></span>Comprar
        </button>
      </article>
    </section>
</template>

<style scoped>

.featured {
  display: flex;
  padding: 3vh 8vw;
  border-bottom: 2px solid #27ae6099;

  & div {
    display: flex;
    align-items: center;
    flex: 1;
    justify-content: center;
    gap: 10px;

    & span {
      font-size: 2rem;
    }

    & h2 {
      font-size: 1.2rem;
      font-weight: 700;
    }
  }

  & article:nth-child(2) {
    border-left: 1px solid #27ae6099;
    border-right: 1px solid #27ae6099;
  }
}</style>
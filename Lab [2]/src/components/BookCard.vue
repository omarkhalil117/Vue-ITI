<template>
  <div class="card mb-4 h-100 mt-3 shadow-sm">
    <img
      :src="book.image"
      class="card-img-top"
      alt="Book Cover"
      style="width: 350px; height: 250px; object-fit: fill"
    />
    <div class="card-body d-flex flex-column justify-content-between">
      <h5 class="card-title text-center">{{ book.name }}</h5>
      <div class="d-flex justify-content-between">
        <div>
          <p class="card-text">Author: {{ book.author }}</p>
          <p class="card-text">
            Category: {{ book.category }}
          </p>
        </div>
        <div>
          <div :class="{'more': book.numberOfPages>200 , 'less': book.numberOfPages<300}">
            <p>{{ book.numberOfPages }} page</p>
          </div>
          <p class="card-text">
            Price: {{Intl.NumberFormat("ar-SA", {style: "currency",currency: "SAR",}).format(book.price)}}
          </p>
        </div>
      </div>
      <button @click.prevent class="btn btn-primary mt-3 align-self-end  btn-sm" @click="addToWishlist(book)">Add to Wish List</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["book", "addToWishlist", "formatPrice"],
  mounted() {
    console.log(this.book.image);
  },
};
</script>

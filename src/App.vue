<script setup>
const picks = [
  {
    number: "01",
    name: "Charred leeks, hazelnut, lemon cream",
    price: 18,
  },
  {
    number: "02",
    name: "Roasted cod, fennel broth, spring herbs",
    price: 34,
  },
  {
    number: "03",
    name: "Olive oil cake, citrus, whipped mascarpone",
    price: 14,
  },
];

const combinedPrice = picks.reduce((total, pick) => total + pick.price, 0);
</script>

<template>
  <main class="cover">
    <nav class="topbar" aria-label="Main navigation">
      <a class="brand" href="#">Maribel Table</a>
      <div class="nav-links">
        <a href="#menu">Menu</a>
        <a href="#hours">Hours</a>
        <a href="#visit">Visit</a>
      </div>
      <a class="reserve-link" href="#reserve">Reserve</a>
    </nav>

    <section class="hero" aria-label="Restaurant cover">
      <div class="hero-content">
        <p class="eyebrow">Seasonal neighborhood dining</p>
        <h1>Maribel Table</h1>
        <p class="lede">
          Enjoy wood-fired dishes, fresh market ingredients, and warm service in
          a relaxed dining room.
        </p>
        <div class="actions">
          <a class="button primary" href="#reserve">Book a table</a>
          <a class="button secondary" href="#menu">View menu</a>
        </div>
      </div>

      <aside class="service-panel" aria-label="Restaurant details">
        <div>
          <span>Dinner</span>
          <strong>Tue-Sun, 5:00-10:30</strong>
        </div>
        <div>
          <span>Chef's Menu</span>
          <strong>Four courses, $78</strong>
        </div>
        <div>
          <span>Location</span>
          <strong>18 Waverly Lane</strong>
        </div>
      </aside>
    </section>
  </main>

  <section class="preview" id="menu" aria-label="Menu preview">
    <p>Tonight's picks</p>
    <div class="preview-grid">
      <article v-for="pick in picks" :key="pick.number">
        <span>{{ pick.number }}</span>
        <h2>{{ pick.name }}</h2>
        <div class="price-row">
          <div>
            <small>Course price</small>
            <strong>${{ pick.price }}</strong>
          </div>
          <div>
            <small>Meal total</small>
            <strong>${{ combinedPrice }}</strong>
          </div>
        </div>
      </article>
    </div>
  </section>
</template>

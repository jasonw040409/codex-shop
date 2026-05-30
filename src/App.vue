<script setup>
const picks = [
  {
    number: "01",
    course: "Ember Garden",
    intro:
      "Charred leeks with toasted hazelnut, Meyer lemon cream, and winter greens.",
    price: 18,
  },
  {
    number: "02",
    course: "Harbor Cod",
    intro:
      "Roasted cod served over fennel broth with spring herbs and arbequina oil.",
    price: 34,
  },
  {
    number: "03",
    course: "Citrus Hour",
    intro:
      "Olive oil cake with blood orange, whipped mascarpone, and candied zest.",
    price: 14,
  },
];

const coverSections = [
  {
    title: "From the Hearth",
    detail: "Live-fire vegetables, roasted fish, and shareable mains finished over oak.",
  },
  {
    title: "Market Pour",
    detail: "Old World bottles, low-intervention favorites, and citrus-led aperitifs.",
  },
  {
    title: "Room for Gatherings",
    detail: "A warm dining room for weeknight dinners, birthdays, and quiet celebrations.",
  },
];
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
        <p class="hero-title">Wood-fired supper, market-led plates, easy hospitality.</p>
        <p class="lede">
          A relaxed dining room built around oak-fired cooking, bright produce,
          and the kind of service that lets a weeknight meal linger.
        </p>
        <div class="actions">
          <a class="button primary" href="#reserve">Book a table</a>
          <a class="button secondary" href="#menu">View menu</a>
        </div>

        <div class="cover-sections" aria-label="Cover highlights">
          <article v-for="section in coverSections" :key="section.title">
            <h2>{{ section.title }}</h2>
            <p>{{ section.detail }}</p>
          </article>
        </div>
      </div>

      <aside class="service-panel" aria-label="Restaurant details">
        <div>
          <span>Evening Service</span>
          <strong>Tuesday-Sunday, 5:00-10:30</strong>
        </div>
        <div>
          <span>Seasonal Tasting</span>
          <strong>Four-course chef's menu, $78</strong>
        </div>
        <div>
          <span>Neighborhood Corner</span>
          <strong>18 Waverly Lane, West Market</strong>
        </div>
      </aside>
    </section>
  </main>

  <section class="preview" id="menu" aria-label="Menu preview">
    <p>Tonight's Featured Plates</p>
    <div class="preview-grid">
      <article v-for="pick in picks" :key="pick.number">
        <span>{{ pick.number }}</span>
        <h2>{{ pick.course }}</h2>
        <p class="course-intro">{{ pick.intro }}</p>
        <div class="price-row">
          <div>
            <small>Course price</small>
            <strong>${{ pick.price }}</strong>
          </div>
        </div>
      </article>
    </div>
  </section>
</template>

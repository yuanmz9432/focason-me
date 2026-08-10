<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'

const year = new Date().getFullYear()
const isScrolled = ref(false)

const updateScroll = () => {
  isScrolled.value = window.scrollY > 24
}

onMounted(() => window.addEventListener('scroll', updateScroll, { passive: true }))
onBeforeUnmount(() => window.removeEventListener('scroll', updateScroll))
</script>

<template>
  <div class="site-shell">
    <header class="nav" :class="{ 'nav--scrolled': isScrolled }">
      <a class="wordmark" href="#top" aria-label="Focason home">focason<span>.</span></a>
      <nav aria-label="Main navigation">
        <a href="#about">About</a>
        <a href="#now">Now</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <main id="top">
      <section class="hero" aria-labelledby="hero-title">
        <p class="eyebrow reveal reveal--one">Yuan Mingze · Tokyo</p>
        <h1 id="hero-title" class="reveal reveal--two">
          Building thoughtful<br />
          <em>digital experiences.</em>
        </h1>
        <div class="hero-bottom reveal reveal--three">
          <p>
            I explore the space between code, artificial intelligence, and useful products.
          </p>
          <a class="circle-link" href="#about" aria-label="Read more about me">
            <svg viewBox="0 0 24 24" aria-hidden="true">
              <path d="M12 4v16M6 14l6 6 6-6" />
            </svg>
          </a>
        </div>
        <div class="orb" aria-hidden="true"><span></span></div>
      </section>

      <section id="about" class="section about">
        <p class="section-label">01 / About</p>
        <div class="section-content">
          <h2>I care about clarity, craft, and making technology feel human.</h2>
          <p class="body-copy">
            I’m Yuan Mingze, the person behind Focason. This is my small corner of the internet—a
            place for ideas, experiments, and things I’m proud to build.
          </p>
        </div>
      </section>

      <section id="now" class="section now">
        <p class="section-label">02 / Now</p>
        <div class="section-content">
          <div class="now-grid">
            <article>
              <span>Exploring</span>
              <h3>AI as a creative partner</h3>
              <p>Finding practical ways for people and intelligent tools to think and make together.</p>
            </article>
            <article>
              <span>Building</span>
              <h3>Simple products with care</h3>
              <p>Turning early ideas into focused, useful experiences—one thoughtful detail at a time.</p>
            </article>
            <article>
              <span>Learning</span>
              <h3>Systems that scale quietly</h3>
              <p>Growing the engineering foundations that let good digital work stay fast and reliable.</p>
            </article>
          </div>
        </div>
      </section>

      <section id="contact" class="contact">
        <p class="section-label">03 / Contact</p>
        <div>
          <p>Have an idea worth exploring?</p>
          <a href="https://github.com/yuanmz9432" target="_blank" rel="noreferrer">
            Let’s connect
            <svg viewBox="0 0 24 24" aria-hidden="true">
              <path d="M5 19 19 5M8 5h11v11" />
            </svg>
          </a>
        </div>
      </section>
    </main>

    <footer>
      <p>© {{ year }} Yuan Mingze</p>
      <p>Made with Vue · Tokyo, Japan</p>
      <a href="#top">Back to top ↑</a>
    </footer>
  </div>
</template>

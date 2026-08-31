<script setup lang="ts">
const technologies = [
  { name: 'HTML5', icon: 'html5' },
  { name: 'CSS3', icon: 'css' },
  { name: 'Tailwind CSS', icon: 'tailwindcss' },
  { name: 'JavaScript', icon: 'javascript' },
  { name: 'TypeScript', icon: 'typescript' },
  { name: 'Vue.js', icon: 'vuedotjs' },
  { name: 'Nuxt.js', icon: 'nuxt' },
  { name: 'Next.js', icon: 'nextdotjs' },
  { name: 'Laravel', icon: 'laravel' },
  { name: 'Livewire', icon: 'livewire' },
  { name: 'Alpine.js', icon: 'alpinedotjs' },
  { name: 'Inertia.js', icon: 'inertia' },
  { name: 'Rust', icon: 'rust' },
  { name: 'GoLang', icon: 'go' },
  { name: 'Virtual Machines', icon: 'virtualbox' },
  { name: 'Git', icon: 'git' },
  { name: 'GitHub', icon: 'github' },
  { name: 'FreeBSD', icon: 'freebsd' },
  { name: 'Ubuntu', icon: 'ubuntu' },
  { name: 'Red Hat', icon: 'redhat' },
  { name: 'Docker', icon: 'docker' },
  { name: 'Podman', icon: 'podman' },
  { name: 'AWS', image: 'https://a0.awsstatic.com/libra-css/images/logos/aws_logo_smile_1200x630.png' },
  { name: 'Laravel Cloud', icon: 'laravel' },
  { name: 'Laravel Forge', icon: 'laravel' },
  { name: 'MySQL', icon: 'mysql' },
  { name: 'PostgreSQL', icon: 'postgresql' },
  { name: 'Meilisearch', icon: 'meilisearch' },
  { name: 'Typesense', image: 'https://typesense.org/assets/images/typesense_logo.svg' },
  { name: 'Laravel Reverb', icon: 'laravel' },
  { name: 'Cloud Code', icon: 'googlecloud' },
  { name: 'Gemini', icon: 'googlegemini' },
  { name: 'Cloudflare', icon: 'cloudflare' }
]

useHead({
  title: 'Avia — Së shpejti online',
  meta: [
    { name: 'robots', content: 'noindex' },
    {
      name: 'description',
      content: 'Avia po rindërtohet. Së shpejti online me një version të përditësuar të sistemeve dhe shërbimeve tona.'
    }
  ]
})
</script>

<template>
  <main class="site-holding">
    <header class="header">
      <img class="logo" src="/logo.svg" alt="Avia">
      <p class="status"><span />Në rindërtim</p>
    </header>

    <section class="content" aria-labelledby="page-title">
      <p class="eyebrow">Një fillim i ri</p>
      <h1 id="page-title">Po ndërtojmë<br><em>diçka më të mirë.</em></h1>
      <p class="lead">
        Jemi duke përditësuar sistemet dhe shërbimet tona për t'ju sjellë një përvojë më të shpejtë dhe më të mirë.
      </p>
      <p class="arrival">Së shpejti online</p>

      <section class="technology-update" aria-labelledby="technology-title">
        <p id="technology-title" class="technology-title">Përditësim i teknologjive</p>
        <ul class="technology-list" aria-label="Teknologjitë që po përditësojmë">
          <li v-for="technology in technologies" :key="technology.name">
            <img
              :src="technology.image || `https://cdn.simpleicons.org/${technology.icon}/171512`"
              :alt="`${technology.name} logo`"
              width="20"
              height="20"
            >
            <span>{{ technology.name }}</span>
          </li>
        </ul>
      </section>
    </section>

    <footer>© {{ new Date().getFullYear() }} Avia</footer>
  </main>
</template>

<style scoped>
:global(*) {
  box-sizing: border-box;
}

:global(body) {
  margin: 0;
  background: #f5f1ea;
}

.site-holding {
  --ink: #171512;
  --orange: #e08000;
  min-height: 100dvh;
  overflow: hidden;
  position: relative;
  min-height: 100dvh;
  display: flex;
  flex-direction: column;
  padding: 2.25rem clamp(1.5rem, 5vw, 5.5rem) 1.75rem;
  color: var(--ink);
  background-color: #f5f1ea;
  background-image: linear-gradient(rgba(23, 21, 18, 0.075) 1px, transparent 1px), linear-gradient(90deg, rgba(23, 21, 18, 0.075) 1px, transparent 1px);
  background-size: 44px 44px;
  font-family: Georgia, 'Times New Roman', serif;
}

.site-holding::after {
  position: absolute;
  width: min(52vw, 46rem);
  aspect-ratio: 1;
  right: min(-18vw, -9rem);
  bottom: min(-31vw, -14rem);
  border: 2px solid var(--orange);
  border-radius: 50%;
  box-shadow: 0 0 0 2rem #f5f1ea, 0 0 0 calc(2rem + 2px) var(--orange);
  content: '';
  pointer-events: none;
}

.header,
.content,
footer {
  position: relative;
  z-index: 1;
}

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  width: 6.4rem;
  height: auto;
}

.status,
.eyebrow,
.arrival,
footer {
  margin: 0;
  font-family: ui-monospace, 'SFMono-Regular', Consolas, monospace;
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

.status {
  display: flex;
  align-items: center;
  gap: 0.55rem;
}

.status span {
  display: block;
  width: 0.55rem;
  aspect-ratio: 1;
  background: var(--orange);
  border-radius: 50%;
  animation: pulse 1.8s ease-in-out infinite;
}

.content {
  width: min(100%, 51rem);
  margin: auto 0;
  padding: 5rem 0;
}

.eyebrow {
  color: var(--orange);
}

h1 {
  max-width: 48rem;
  margin: 1.2rem 0 1.7rem;
  font-size: clamp(3.4rem, 8vw, 7.5rem);
  font-weight: 500;
  line-height: 0.92;
  letter-spacing: 0;
}

h1 em {
  color: var(--orange);
  font-style: italic;
}

.lead {
  max-width: 35rem;
  margin: 0;
  font-size: clamp(1.05rem, 1.8vw, 1.3rem);
  line-height: 1.5;
}

.arrival {
  display: inline-block;
  margin-top: 2.4rem;
  padding-bottom: 0.45rem;
  border-bottom: 2px solid var(--orange);
}

.technology-update {
  max-width: 44rem;
  margin-top: 3rem;
}

.technology-title {
  margin: 0 0 0.9rem;
  font-family: ui-monospace, 'SFMono-Regular', Consolas, monospace;
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

.technology-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.55rem;
  margin: 0;
  padding: 0;
  list-style: none;
}

.technology-list li {
  display: inline-flex;
  align-items: center;
  gap: 0.45rem;
  min-height: 2.35rem;
  padding: 0.45rem 0.7rem;
  border: 1px solid rgba(23, 21, 18, 0.23);
  background: rgba(245, 241, 234, 0.78);
  font-family: ui-monospace, 'SFMono-Regular', Consolas, monospace;
  font-size: 0.72rem;
  font-weight: 700;
  line-height: 1;
  white-space: nowrap;
}

.technology-list img {
  display: block;
  width: 1rem;
  height: 1rem;
}

footer {
  color: rgba(23, 21, 18, 0.7);
}

@keyframes pulse {
  50% {
    transform: scale(0.65);
    opacity: 0.45;
  }
}

@media (max-width: 520px) {
  .site-holding {
    padding-top: 1.5rem;
  }

  .logo {
    width: 5.5rem;
  }

  .status {
    font-size: 0.62rem;
  }

  .content {
    padding: 3rem 0 2rem;
  }

  .technology-update {
    margin-top: 2.4rem;
  }

  .technology-list {
    gap: 0.45rem;
  }

  .technology-list li {
    min-height: 2.2rem;
    padding: 0.4rem 0.55rem;
    font-size: 0.66rem;
  }

  .site-holding::after {
    width: 18rem;
    right: -10rem;
    bottom: -7.5rem;
  }
}
</style>

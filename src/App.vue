
<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)

const skills = [
  'HTML & CSS',
  'JavaScript',
  'Vue.js',
  'C++',
  'Arduino',
  'Computer Hardware',
]

const projects = [
  {
    number: '01',
    title: 'Wearable Sign-to-Speech Glove',
    description:
        'A wearable project that uses sensors and edge AI to help translate sign gestures into speech.',
    tools: 'Embedded Systems · Sensors · Edge AI',
  },
  {
    number: '02',
    title: 'Adaptive Pedestrian Crossing',
    description:
        'A traffic light concept using NFC technology to provide additional crossing time for eligible pedestrians.',
    tools: 'Arduino · NFC · Electronics',
  },
  {
    number: '03',
    title: 'Personal E-Portfolio',
    description:
        'A personal website built to showcase my skills, projects, certificates, and contact information.',
    tools: 'Vue.js · Tailwind CSS · Vite',
  },
]

const certificates = [
  {
    title: 'Certificate 01',
    issuer: 'Replace with the issuing organization',
    file: '/118.png',
  },
  {
    title: 'Certificate 02',
    issuer: 'Replace with the issuing organization',
    file: '/Tabaldo.png',
  },
]
</script>

<template>
  <div class="min-h-screen bg-[#f8f2e8] text-[#292322]">

    <!-- Navigation -->
    <header class="border-b border-[#e7d9ca]">
      <nav
          class="mx-auto flex max-w-6xl items-center justify-between px-5 py-5 md:px-8"
      >
        <a href="#home" class="text-xl font-black tracking-tight">
          YVAN<span class="text-[#a52d35]">.</span>
        </a>

        <button
            class="rounded-lg border border-[#dfcfc0] px-3 py-2 text-sm md:hidden"
            @click="menuOpen = !menuOpen"
            :aria-expanded="menuOpen"
            aria-label="Toggle navigation"
        >
          {{ menuOpen ? 'Close' : 'Menu' }}
        </button>

        <div
            class="hidden items-center gap-7 text-sm font-medium md:flex"
        >
          <a href="#about" class="hover:text-[#a52d35]">About</a>
          <a href="#projects" class="hover:text-[#a52d35]">Projects</a>
          <a href="#certificates" class="hover:text-[#a52d35]">
            Certificates
          </a>
          <a href="#contact" class="hover:text-[#a52d35]">Contact</a>
          <a
              href="/cv/Yvan-Tabaldo-CV.pdf"
              download
              class="rounded-full bg-[#a52d35] px-5 py-3 text-white transition hover:bg-[#812129]"
          >
            Download CV ↗
          </a>
        </div>
      </nav>

      <div
          v-if="menuOpen"
          class="flex flex-col gap-4 border-t border-[#e7d9ca] px-5 py-5 md:hidden"
      >
        <a href="#about" @click="menuOpen = false">About</a>
        <a href="#projects" @click="menuOpen = false">Projects</a>
        <a href="#certificates" @click="menuOpen = false">Certificates</a>
        <a href="#contact" @click="menuOpen = false">Contact</a>
        <a
            href="/cv/Yvan-Tabaldo-CV.pdf"
            download
            class="font-bold text-[#a52d35]"
        >
          Download CV ↗
        </a>
      </div>
    </header>

    <main>
      <!-- Hero -->
      <section
          id="home"
          class="mx-auto grid max-w-6xl items-center gap-12 px-5 py-20 md:grid-cols-2 md:px-8 md:py-28"
      >
        <div>
          <p
              class="mb-6 inline-flex items-center gap-2 rounded-full border border-[#e5c9bb] px-4 py-2 text-xs font-bold uppercase tracking-[0.16em] text-[#a52d35]"
          >
            <span class="h-2 w-2 rounded-full bg-[#a52d35]"></span>
            Computer Engineering Student
          </p>

          <h1
              class="max-w-xl text-5xl font-black leading-[1.08] tracking-tight sm:text-6xl lg:text-7xl"
          >
            Hi, I'm Yvan<span class="text-[#a52d35]">.</span>
            <br />
            I build things
            <span class="font-serif font-normal italic">that matter.</span>
          </h1>

          <p class="mt-7 max-w-lg text-base leading-8 text-[#716660]">
            I'm a Computer Engineering student learning to build useful and
            creative technology through programming, electronics, and
            hands-on projects.
          </p>

          <div class="mt-9 flex flex-wrap gap-4">
            <a
                href="#projects"
                class="rounded-full bg-[#a52d35] px-7 py-4 text-sm font-bold text-white transition hover:-translate-y-1 hover:bg-[#812129]"
            >
              Explore My Projects ↗
            </a>

            <a
                href="#contact"
                class="rounded-full border border-[#d8c7b7] px-7 py-4 text-sm font-bold transition hover:border-[#a52d35]"
            >
              Get in Touch
            </a>
          </div>

          <div class="mt-12 flex flex-wrap gap-x-6 gap-y-3 text-sm text-[#716660]">
            <span>⌖ Philippines</span>
            <span>✉ Open to opportunities</span>
          </div>
        </div>

        <div class="relative mx-auto w-full max-w-xs">
          <div
              class="absolute -right-3 -top-3 h-full w-full rounded-[2rem] border-2 border-[#a52d35]"
          ></div>

          <div
              class="relative flex aspect-[4/5] items-center justify-center overflow-hidden rounded-[2rem] bg-[#e9d8c5]">
            <img
                src="/id.jpg"
                alt="Portrait of Yvan"
                class="h-full w-full object-cover"
                @error="(event) => {
                event.target.style.display = 'none'
              }"
            />

            <div class="absolute bottom-5 left-5 right-5 rounded-2xl bg-[#f8f2e8]/95 p-5">
              <p class="text-xs font-bold uppercase tracking-[0.16em] text-[#a52d35]">
                A little about me
              </p>
              <p class="mt-2 text-lg font-bold">
                Learning. Building. Improving.
              </p>
            </div>
          </div>

          <p class="mt-5 text-center text-xs text-[#716660]">
            Curious mind. Hands-on learner. Future engineer.
          </p>
        </div>
      </section>

      <!-- About -->
      <section id="about" class="bg-[#eee3d5]">
        <div class="mx-auto max-w-6xl px-5 py-20 md:px-8 md:py-24">
          <p class="text-xs font-bold uppercase tracking-[0.2em] text-[#a52d35]">
            01 / About me
          </p>

          <div class="mt-6 grid gap-10 md:grid-cols-2">
            <h2 class="text-4xl font-black leading-tight sm:text-5xl">
              A student with a passion for
              <span class="font-serif font-normal italic text-[#a52d35]">
                technology.
              </span>
            </h2>

            <div>
              <p class="leading-8 text-[#716660]">
                I am currently studying Computer Engineering and exploring
                how software and hardware work together. I enjoy creating
                projects, solving problems, and learning new tools that
                turn ideas into something useful.
              </p>

              <p class="mt-4 leading-8 text-[#716660]">
                My goal is to keep improving my skills, gain real-world
                experience, and create technology that can help people.
              </p>

              <a
                  href="/Yvan-Resume.pdf"
                  download
                  class="mt-7 inline-block border-b-2 border-[#a52d35] pb-2 text-sm font-bold"
              >
                View my resume ↓
              </a>
            </div>
          </div>

          <div class="mt-14">
            <h3 class="text-lg font-bold">Skills I'm learning</h3>

            <div class="mt-5 flex flex-wrap gap-3">
              <span
                  v-for="skill in skills"
                  :key="skill"
                  class="rounded-full border border-[#d7c4b1] bg-[#f8f2e8] px-5 py-3 text-sm font-medium"
              >
                {{ skill }}
              </span>
            </div>
          </div>
        </div>
      </section>

      <!-- Projects -->
      <section id="projects" class="mx-auto max-w-6xl px-5 py-20 md:px-8 md:py-24">
        <p class="text-xs font-bold uppercase tracking-[0.2em] text-[#a52d35]">
          02 / Selected work
        </p>

        <div class="mt-5 flex flex-wrap items-end justify-between gap-5">
          <h2 class="text-4xl font-black sm:text-5xl">Featured Projects</h2>
          <p class="max-w-sm text-sm leading-7 text-[#716660]">
            A few projects that show what I'm learning and building along
            the way.
          </p>
        </div>

        <div class="mt-10 grid gap-5 md:grid-cols-2">
          <article
              v-for="project in projects"
              :key="project.number"
              class="rounded-3xl border border-[#e7d9ca] bg-[#fffaf3] p-7 transition hover:-translate-y-1 hover:border-[#c68b82]"
          >
            <div class="flex items-center justify-between">
              <span class="text-sm font-bold text-[#a52d35]">
                PROJECT {{ project.number }}
              </span>
              <span class="text-xl">↗</span>
            </div>

            <h3 class="mt-9 text-2xl font-black">{{ project.title }}</h3>

            <p class="mt-4 leading-7 text-[#716660]">
              {{ project.description }}
            </p>

            <p class="mt-6 border-t border-[#e7d9ca] pt-5 text-xs font-bold uppercase tracking-wide text-[#a52d35]">
              {{ project.tools }}
            </p>
          </article>
        </div>
      </section>

      <!-- Certificates -->
      <section id="certificates" class="bg-[#292322] text-[#f8f2e8]">
        <div class="mx-auto max-w-6xl px-5 py-20 md:px-8 md:py-24">
          <p class="text-xs font-bold uppercase tracking-[0.2em] text-[#e6a39b]">
            03 / Achievements
          </p>

          <div class="mt-5 flex flex-wrap items-end justify-between gap-5">
            <h2 class="text-4xl font-black sm:text-5xl">
              Certificates<span class="text-[#e6a39b]">.</span>
            </h2>
            <p class="max-w-sm text-sm leading-7 text-[#c7b8af]">
              Training, courses, and achievements from my learning journey.
            </p>
          </div>

          <div class="mt-10 grid gap-5 md:grid-cols-2">
            <article
                v-for="certificate in certificates"
                :key="certificate.title"
                class="rounded-2xl border border-[#514441] p-6"
            >
              <div class="flex items-start justify-between gap-4">
                <div>
                  <p class="text-xs uppercase tracking-widest text-[#e6a39b]">
                    Certificate
                  </p>
                  <h3 class="mt-3 text-xl font-bold">
                    {{ certificate.title }}
                  </h3>
                  <p class="mt-2 text-sm text-[#c7b8af]">
                    {{ certificate.issuer }}
                  </p>
                </div>
                <span class="text-2xl">↗</span>
              </div>

              <a
                  :href="certificate.file"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="mt-7 inline-block rounded-full bg-[#f8f2e8] px-5 py-3 text-sm font-bold text-[#292322] hover:bg-[#e6a39b]"
              >
                View Certificate
              </a>
            </article>
          </div>
        </div>
      </section>

      <!-- CV -->
      <section class="mx-auto max-w-6xl px-5 py-16 md:px-8 md:py-20">
        <div
            class="flex flex-col justify-between gap-7 rounded-3xl bg-[#ead8c6] p-8 sm:p-10 md:flex-row md:items-center"
        >
          <div>
            <p class="text-xs font-bold uppercase tracking-[0.2em] text-[#a52d35]">
              Resume / CV
            </p>
            <h2 class="mt-3 text-3xl font-black">
              Want to know more about me?
            </h2>
            <p class="mt-3 text-sm leading-7 text-[#716660]">
              Download my CV to see my education, skills, and experience.
            </p>
          </div>

          <a
              href="/cv/Yvan-Tabaldo-CV.pdf"
              download
              class="shrink-0 rounded-full bg-[#a52d35] px-7 py-4 text-center text-sm font-bold text-white transition hover:bg-[#812129]"
          >
            Download My CV ↓
          </a>
        </div>
      </section>

      <!-- Contact -->
      <section id="contact" class="border-t border-[#e7d9ca]">
        <div class="mx-auto max-w-6xl px-5 py-20 md:px-8 md:py-24">
          <p class="text-xs font-bold uppercase tracking-[0.2em] text-[#a52d35]">
            04 / Contact
          </p>

          <h2 class="mt-5 max-w-2xl text-4xl font-black leading-tight sm:text-6xl">
            Have an idea?
            <span class="font-serif font-normal italic text-[#a52d35]">
              Let's talk.
            </span>
          </h2>

          <p class="mt-5 max-w-lg leading-8 text-[#716660]">
            I'm happy to connect with fellow students, developers, and
            people interested in technology and creative projects.
          </p>

          <div class="mt-10 grid gap-4 sm:grid-cols-2 lg:grid-cols-3">
            <div class="rounded-2xl border border-[#e7d9ca] p-6">
              <p class="text-xs font-bold uppercase tracking-widest text-[#a52d35]">
                Email
              </p>
              <a
                  href="yvandominictabaldo1@gmail.com"
                  class="mt-3 block break-all font-bold hover:text-[#a52d35]"
              >
                yvandominictabaldo1@gmail.com
              </a>
            </div>

            <div class="rounded-2xl border border-[#e7d9ca] p-6">
              <p class="text-xs font-bold uppercase tracking-widest text-[#a52d35]">
                Phone
              </p>
              <a
                  href="tel:+639663251745"
                  class="mt-3 block font-bold hover:text-[#a52d35]"
              >
                +63 966 325 1745
              </a>
            </div>

            <div class="rounded-2xl border border-[#e7d9ca] p-6">
              <p class="text-xs font-bold uppercase tracking-widest text-[#a52d35]">
                Location
              </p>
              <p class="mt-3 font-bold">Tuguegarao City, Philippines</p>
            </div>
          </div>

          <div class="mt-8 flex flex-wrap gap-5 text-sm font-bold">
            <a
                href="mailto:your.email@example.com"
                class="text-[#a52d35] hover:underline"
            >
              Send me an email ↗
            </a>
            <a
                href="/cv/Yvan-Tabaldo-CV.pdf"
                download
                class="hover:text-[#a52d35]"
            >
              Get my CV ↓
            </a>
          </div>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <footer class="border-t border-[#e7d9ca]">
      <div
          class="mx-auto flex max-w-6xl flex-col gap-3 px-5 py-7 text-sm text-[#716660] sm:flex-row sm:items-center sm:justify-between md:px-8"
      >
        <p>© {{ new Date().getFullYear() }} Yvan Tabaldo</p>
        <p>Made with care, coffee, and code.</p>
        <a href="#home" class="font-bold text-[#a52d35]">Back to top ↑</a>
      </div>
    </footer>
  </div>
</template>

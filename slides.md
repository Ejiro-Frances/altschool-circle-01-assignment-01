---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: #000000
# some information about your slides (markdown enabled)
title: Circle one Assignment
info: |
  ## Slidev Starter Template
  Presentation slides for Circle one.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
hideInToc: true
---

# [Circle one]{.text-8xl.font-hand.text-teal-900}

Presentation slides for Assignment one

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
hideInToc: true
---

## [Circle One members]{.text-teal-400}

- Busari Olanrewaju
- Esther Oluwatimilehin
- Reuben Agbor
- Elinah Mmbone
- Ejiro Francess Ejoh
- Salaudeen Rukayat Temitope
- Doris Senyah Afriyie
- Name
- Name
- Name

---
hideInToc: true
---

# [Table of contents]{.text-teal-400}

<!-- You can use the `Toc` component to generate a table of contents for your slides: -->

<Toc minDepth="1" maxDepth="1" />

---
class: text-sm
---

# [Introduction]{.text-teal-400}

In the First Week we discussed about using Learning How To Learn, Frontend HandBook and Refactoring UI Book

<h2 class= "text-teal-400">Learning How To Learn </h2>

Learning how to learn means improving your ability to acquire and retain knowledge by understanding how your mind works. It involves: Metacognition: Being aware of and managing your learning strategies, Effective Techniques: Using spaced repetition, active recall, interleaving, and elaboration, Strategy Over Style: Choosing the right method for the material, not relying on learning "styles.", Feedback & Reflection: Regularly assessing and adjusting your approach, Environment & Motivation: Staying focused with clear goals and a good setup.

It’s about learning smarter, not just harder.

Would you like a visual cheat sheet of these principles?

[Learning how to Learn](https://www.coursera.org/learn/learning-how-to-learn?)

<!-- Inline style -->
<style>
.footnotes-sep {
  @apply mt-5 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

---
class: text-sm
---

<h2 class= "text-teal-400" >Frontend HandBook </h2>

The Frontend Handbook is a guide that outlines best practices, tools, and knowledge areas for frontend developers. It serves as a roadmap for learning and improving in frontend development.

Key Components:
Foundational Skills: Covers HTML, CSS, and JavaScript—the core of frontend.

Frameworks & Libraries: Introduces tools like React, Vue, or Angular.

Tooling: Explains bundlers (Webpack, Vite), package managers, version control (Git), etc.

Performance & Accessibility: Emphasizes speed and inclusive design.

Architecture & Design Patterns: Guides you in building scalable, maintainable codebases.

Testing & Deployment: Covers how to test code and ship to production.

Career & Collaboration: Offers advice on working in teams, communication, and job roles.

It’s like a map for becoming a competent frontend developer—from beginner to advanced.

#### [Frontend HandBook](https://frontendmasters.com/guides/front-end-handbook/2024/)

---
class: text-sm
---

<h2 class= "text-teal-400"> Refactoring UI </h2>

Refactoring UI is a design guide by Adam Wathan and Steve Schoger that teaches developers how to create beautiful, usable interfaces—without needing to be a designer.

Core Ideas:
Design isn’t just about visuals—it's about clarity, hierarchy, and usability.

Small tweaks = big impact: Improving spacing, alignment, contrast, and typography can transform a UI.

Start with structure: Get layout and content right before worrying about colors or details.

Use systems: Consistent spacing, font sizes, and color scales make design easier and better.

Refactor like code: Improve UI in iterations, just like refactoring messy code.

Key Topics:
Visual hierarchy,
Spacing and layout,
Color usage and contrast,
Typography,
Reusable design patterns,
Real-world before/after UI makeovers

It’s especially useful for developers who want to level up their UI instincts without formal design training.

---
src: ./pages/function.md
---

---
src: ./pages/loops.md
---

---
src: ./pages/array.md
---

---
src: ./pages/promises.md
---

---
src: ./pages/events.md
---

---
src: ./pages/modules.md
---

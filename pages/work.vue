<template>
 <div class="bg-black h-screen px-6 py-12">
    <h2
      class="text-white font-exo text-5xl opacity-0"
      ref="title"
      style="transform: translateY(30px)"
    >
      WORK
    </h2>

    <div class="flex space-x-4">
      <div
        ref="projects"
        v-for="project in projects"
        class="w-full opacity-0"
        style="transform: translateX(30px)"
      >
        <a href="https://github.com/Matt-Chisholm">
          <img
            :src="project.image.url"
            alt="iPhone"
            style="height: 70vh; border-radius: 3em;"
            class="object-cover"
          />
          <p class="text-white font-space-mono text-sm">{{ project.title }}</p>
        </a>
      </div>
    </div>
    </div>
</template>

<script>
import gsap from 'gsap'
import tweeterImg from '~/assets/Tweeter.jpg.png';
import iphoneImg from '~/assets/iphone.jpg'
import laptopImg from '~/assets/laptop.jpg'
import personImg from '~/assets/person.jpg'
export default {
  data() {
    return {
      projects: [
        {
          image: {
            url: iphoneImg
          },
          title: 'Github : Matt-Chisholm'
        },
        {
          image: {
            url: laptopImg
          },
          title: 'Twatch (Twitch Clone)'
        },
        {
          image: {
            url: personImg
          },
          title: 'Paw-Five'
        },
        {
            image: {
                url: tweeterImg
            },
            title: 'Tweeter'
        }
      ]
    }
  },
  mounted() {
    gsap.to(this.$refs.title, {
      opacity: 1,
      duration: 1.5,
      y: 0,
      ease: 'expo'
    })
    gsap.to(this.$refs.projects, {
      opacity: 1,
      duration: 1.5,
      stagger: 0.1,
      x: 0,
      ease: 'expo',
      delay: 0.2
    })
  }
}
</script>
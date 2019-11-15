<template>
  <div class="container mx-auto px-4 text-center pb-4 md:pb-8 lg:pb-16">
    <h1 class="text-2xl mt-4 md:mt-8 lg:mt-16 mb-1 text-gray-700">Projects</h1>
    <h3 class="text-xs font-light mb-6 md:mb-12">Full-stack Web Development</h3>
    <div class="px-4 flex justify-center mb-6 md:mb-12">
      <img class="w-7/12 md:w-5/12 lg:w-4/12" src="~/assets/img/functions.svg" alt="functions" />
    </div>

    <div
      class="w-full md:w-1/2 mb-4 mx-auto text-left font-light border border-gray-300 shadow bg-gray-200 p-4 rounded"
      v-for="project in projects"
      :key="project.id"
    >
      <a :href="project.links.visit" target="_blank">
        <h3 class="text-xl font-bold">{{ project.name }}</h3>
      </a>
      <p v-html="project.description"></p>
      <div class="flex justify-start mt-4">
        <a
          class="text-blue-500 mr-3"
          target="_blank"
          :href="project.links.visit"
          v-if="project.links.visit"
        >visit</a>
        <a
          class="text-blue-500 mr-3"
          target="_blank"
          :href="project.links.github"
          v-if="project.links.github"
        >github</a>
        <a
          class="text-blue-500 mr-3"
          target="_blank"
          :href="project.links.docs"
          v-if="project.links.docs"
        >docs</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          id: 'valform',
          name: 'Valform JS',
          description:
            "Valform is lightweight javascript form validation library (26kb minified, 8kb gzip). It does not have any dependencies, it's fully customizable and provides some basic validation methods and also tools to easily change/add different methods to your liking and needs. It would also accept asynchronous validation methods. <span class='text-teal-600'>#es6 #webpack #npm",
          links: {
            github: 'https://github.com/radoslavtomas/valForm',
            visit: 'https://valformjs.com/',
            docs: 'https://valformjs.com/docs'
          }
        },
        {
          id: 'kit',
          name: 'Simple Vue Input Kit',
          description:
            'This is a Vue JS plugin build on the top of Valform JS library. Custom input fields that can be reused in more projects. <span class="text-teal-600">#vue #webpack #npm</span>',
          links: {
            visit: 'https://inputkit.valformjs.com/'
          }
        },
        {
          id: 'ftball',
          name: 'Football Slayer',
          description:
            "Football. Just because I don't get it - doesn't mean I won't accept it. But what I refuse to accept are traffic jams before and after any match. This simple application emerged out of a frustration when commuting from Liverpool to Manchester and back. The main purpose is to track date and time of football matches near you so you can avoid traffic jams. <span class='text-teal-600'>#vue</span>",
          links: {
            github: 'https://github.com/radoslavtomas/footballslayer',
            visit: 'https://footballslayer.com/'
          }
        },
        {
          id: 'poetry',
          name: 'Radoslav Tomas - Poet',
          description:
            'This is my personal website where I present myself from a different angle - as a poet. Unfortunately, these days more as a reader than a writer. But poetry is still a big part of my life. <span class="text-teal-600">#vue #laravel</span>',
          links: {
            github: 'https://github.com/radoslavtomas/radoslav_poetry_vue',
            visit: 'https://radoslavtomas.com/'
          }
        },
        {
          id: 'pckt',
          name: 'Pocket',
          description:
            'Pocket is a PWA private project to track any income and expenses if you work as a freelancer or have a private practise. It was made to measure application so there are no outside registrations. Features cover normal CRUD operations on transactions, creation of reports, setting up a tax days, printing reports... Build with Vue JS and Firebase. <span class="text-teal-600">#vue #firebase #pwa</span>',
          links: {
            visit: 'https://pocketapp.space/'
          }
        },
        {
          id: 'dtb',
          name: 'Dancing The Blues',
          description:
            'Website for Edge Hill University project. It contained custom backend system to manage content and blog. As the project is idle these days the app is archived in a form of a static website. <span class="text-teal-600">#laravel</span>',
          links: {
            github: '',
            visit: 'https://dancingtheblues.org/',
            docs: 'https://github.com/radoslavtomas/dancingtheblues-static'
          }
        },
        {
          id: 'qld',
          name: 'MyQuotes Quoteline Direct',
          description:
            'This is a visible part of my professional work. Quoting system made to measure for Quoteline Direct insurance broker. <span class="text-teal-600">#laravel #vue</span>',
          links: {
            visit:
              'https://myquotesv4.quotelinedirect.co.uk/PC/your-details?B=INQQ&R=INQL&RAF='
          }
        },
        {
          id: 'innland',
          name: 'Inner Landscapes',
          description:
            'Simple website that serves as a business e-card. <span class="text-teal-600">#vue</span>',
          links: {
            github: 'https://github.com/radoslavtomas/innerlandscapes',
            visit: 'https://innerlandscapes.org/'
          }
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
</style>

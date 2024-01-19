
```markdown
**App.vue**

```vue
<template>
  <div>
    <!-- Your main content goes here -->

    <h1>Welcome to Your Vue.js App!</h1>
    <!-- ... -->

    <!-- Use the SEO component with relevant data -->
    <seo
      :title="pageTitle"
      :description="pageDescription"
      :keywords="pageKeywords"
      :image="pageImage"
      :url="pageUrl"
      :author="pageAuthor"
      :siteName="siteName"
      :twitterUsername="twitterUsername"
      :canonicalUrl="canonicalUrl"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      pageTitle: 'Your Page Title',
      pageDescription: 'Your page description goes here.',
      pageKeywords: 'keyword1, keyword2, keyword3',
      pageImage: 'url_to_your_featured_image.jpg',
      pageUrl: 'https://www.yourwebsite.com',
      pageAuthor: 'Your Name',
      siteName: 'Your Website Name',
      twitterUsername: '@yourTwitterHandle',
      canonicalUrl: 'https://www.yourwebsite.com/canonical-path',
    };
  },
};
</script>

<style>
/* Your component styles go here */
</style>
```

**SEO.vue**

```vue
<template>
  <vue-meta
    :title="title"
    :meta="meta"
    :link="link"
  />
</template>

<script>
export default {
  props: {
    title: String,
    description: String,
    keywords: String,
    image: String,
    url: String,
    author: String,
    siteName: String,
    twitterUsername: String,
    canonicalUrl: String,
  },
  computed: {
    meta() {
      return [
        { vmid: 'description', name: 'description', content: this.description },
        { vmid: 'keywords', name: 'keywords', content: this.keywords },
        { vmid: 'og:title', property: 'og:title', content: this.title },
        { vmid: 'og:description', property: 'og:description', content: this.description },
        { vmid: 'og:image', property: 'og:image', content: this.image },
        { vmid: 'og:url', property: 'og:url', content: this.url },
        { vmid: 'og:site_name', property: 'og:site_name', content: this.siteName },
        { vmid: 'og:type', property: 'og:type', content: 'website' },
        { vmid: 'twitter:card', name: 'twitter:card', content: 'summary_large_image' },
        { vmid: 'twitter:title', name: 'twitter:title', content: this.title },
        { vmid: 'twitter:description', name: 'twitter:description', content: this.description },
        { vmid: 'twitter:image', name: 'twitter:image', content: this.image },
        { vmid: 'twitter:site', name: 'twitter:site', content: this.twitterUsername },
        { vmid: 'twitter:creator', name: 'twitter:creator', content: this.twitterUsername },
        { vmid: 'viewport', name: 'viewport', content: 'width=device-width, initial-scale=1.0' },
        { vmid: 'httpEquiv', name: 'httpEquiv', content: 'Content-Type', charset: 'utf-8' },
        { vmid: 'robots', name: 'robots', content: 'index, follow' },
        { vmid: 'author', name: 'author', content: this.author },
      ];
    },
    link() {
      return this.canonicalUrl ? [{ vmid: 'canonical', rel: 'canonical', href: this.canonicalUrl }] : [];
    },
  },
};
</script>

<style scoped>
/* Your component styles go here */
</style>
```

**main.js**

```javascript
// main.js

import Vue from 'vue';
import App from './App.vue';
import Meta from 'vue-meta';

Vue.use(Meta);

new Vue({
  render: (h) => h(App),
}).$mount('#app');
```

Please note that when working with Vue.js components, the Vue template syntax might not render accurately in Markdown viewers. Copy and paste the code into your Vue.js project files for proper rendering.

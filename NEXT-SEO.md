**pages/\_app.js** (or a layout component used across pages):

```jsx
// Import necessary modules
import { useEffect } from 'react';
import { DefaultSeo } from 'next-seo';
import SEO from '../components/SEO';

// Custom App component
function MyApp({ Component, pageProps }) {
  // Add a global effect to set up SEO for all pages
  useEffect(() => {
    // You can add global SEO configurations here
  }, []);

  return (
    <>
      {/* Set up default SEO for all pages */}
      <DefaultSeo {...SEO} />

      {/* Render the main component */}
      <Component {...pageProps} />
    </>
  );
}

export default MyApp;
```

**components/SEO.js**:

```jsx
// SEO component for setting up meta tags
const SEO = {
  title: 'Your Website Title',
  description: 'Your website description goes here.',
  canonical: 'https://www.yourwebsite.com',
  openGraph: {
    type: 'website',
    url: 'https://www.yourwebsite.com',
    title: 'Your Website Title',
    description: 'Your website description goes here.',
    images: [
      {
        url: 'url_to_your_featured_image.jpg',
        alt: 'Your Image Alt Text',
      },
    ],
  },
  twitter: {
    handle: '@yourTwitterHandle',
    site: '@yourTwitterHandle',
    cardType: 'summary_large_image',
  },
};

export default SEO;
```

Make sure to replace placeholder values with your actual content. This setup uses the `next-seo` package for managing SEO in a Next.js application. You can install it using:

```bash
npm install next-seo
```

This example includes features such as:

- Global SEO configurations in the `_app.js` file.
- Default SEO setup for all pages using the `DefaultSeo` component from `next-seo`.
- SEO component (`SEO.js`) with basic meta tags, Open Graph, and Twitter card configurations.

Ensure that you customize the data in the `SEO.js` file based on your specific content and requirements. Keep up with SEO best practices to optimize your website for search engines.

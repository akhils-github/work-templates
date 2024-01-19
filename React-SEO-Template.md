```jsx
# React SEO Component

```jsx
import React from 'react';
import { Helmet } from 'react-helmet';
```

```jsx
const SEO = ({ title, description, keywords, image, url, author, siteName }) => {
  return (
    <Helmet>
      {/* Basic meta tags */}
      <title>{title}</title>
      <meta name="description" content={description} />
      <meta name="keywords" content={keywords} />
```

```jsx
      {/* Open Graph (OG) meta tags */}
      <meta property="og:title" content={title} />
      <meta property="og:description" content={description} />
      <meta property="og:image" content={image} />
      <meta property="og:url" content={url} />
      <meta property="og:site_name" content={siteName} />
      <meta property="og:type" content="website" />
```

```jsx
      {/* Twitter meta tags */}
      <meta name="twitter:card" content="summary_large_image" />
      <meta name="twitter:title" content={title} />
      <meta name="twitter:description" content={description} />
      <meta name="twitter:image" content={image} />
      <meta name="twitter:site" content={author} />
      <meta name="twitter:creator" content={author} />
```

```jsx
      {/* Additional meta tags */}
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <meta httpEquiv="Content-Type" content="text/html; charset=utf-8" />
      <meta name="robots" content="index, follow" />
      <meta name="author" content={author} />
```

```jsx
      {/* Favicon */}
      <link rel="icon" href="/favicon.ico" />
    </Helmet>
  );
};
```

```jsx
# React App Component

```jsx
const App = () => {
  return (
    <div>
      {/* Use the SEO component with relevant data */}
      <SEO
        title="Your Page Title"
        description="Your page description goes here."
        keywords="keyword1, keyword2, keyword3"
        image="url_to_your_featured_image.jpg"
        url="https://www.yourwebsite.com"
        author="Your Name"
        siteName="Your Website Name"
      />
```

```jsx
      {/* Your main content goes here */}
      <h1>Welcome to Your React App!</h1>
      {/* ... */}
    </div>
  );
};

export default App;
```

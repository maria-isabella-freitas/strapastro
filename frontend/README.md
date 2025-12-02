# Lifehacks

## Displaying Lifehacks titles

- use the fetchApi function to get all the lifehacks from Strapi
- You will need to set the .env variable STRAPI_URL to point to your Strapi backend (e.g. <http://localhost:1337>)
- Display the lifehacks in a list, showing the title of the lifehack.

  ```html
  <article>
    <h2>[lifehack title here]</h2>
  </article>
  ```

## Linking to Lifehack details

- Wrap the lifehack aticle in a link to '/lifehacks/[lifehack documentId here]'

## Create the page to show the lifehack details

- Create a new page at src/pages/lifehacks/[id].astro
- Create a getStaticPaths function
  - fetch all lifehacks from Strapi
  - return an array of objects with the params object containing the documentId of each lifehack and the props object containing the lifehack data
- In the page component, display the lifehack title and content

  ```html
  <article>
    <h1>[lifehack title here]</h1>
    <div>[lifehack description here]</div>
  </article>```


## Bonus: categories

- Add a relation field 'category' to the lifehack content type in Strapi
- Create a new content type 'category' with a 'name' field
- Assign categories to lifehacks in Strapi

- Update the lifehack details page to display the category name, linked to the category page

  ```html
  <article>
    <h1>[lifehack title here]</h1>
    <p>Category: <a href="/categories/[category documentId here]">[category name here]</a></p>
    <div>[lifehack description here]</div>
  </article>```

- create a new page at src/pages/categories/[id].astro and start by showing the category name first.
- now make use of the fetchApi query parameter to fetch only the lifehacks that belong to this category.
- display the lifehacks in a list, similar to the homepage.


# 🚀 Next.js Self-Training Diary

### One-Month Learning Log

## 📅 Day 1 – Jul 1

**🏷️ Training Day:** Day 1 of 28
**📚 Topic:** Introduction to Next.js – What it is, Why it exists over plain React, Project setup with `create-next-app`, and Folder structure overview

---

### 🎯 Objective

Understand what Next.js is, why it was created as a framework on top of React, and become familiar with creating a new project and navigating its default structure.

### 📌 Topics Covered

- Purpose of Next.js and the problems it solves compared to a plain React SPA.
- Key built-in features such as file-based routing, server-side capabilities, and performance optimizations.
- Creating a new application using `create-next-app` and understanding the setup options.
- Overview of the default project structure (`app`, `public`, `components`, configuration files, etc.).
- Difference between framework conventions and a manually configured React project.

### 💻 Hands-on / Practice

I initialized a new Next.js project using `create-next-app`, explored the generated folder structure, customized the homepage with a simple introduction, added a reusable `Header` component, and created an `about` route to understand how file-based routing works.

### 📖 Key Learnings

- I understood that Next.js is not a replacement for React but a framework that builds on React with production-ready features already integrated.
- I noticed how much setup work is eliminated compared to configuring a React project from scratch.
- The App Router structure felt organized, and I could quickly identify where pages, layouts, and static assets belong.
- I realized that following the framework's conventions makes projects easier to scale and maintain.

### ⚡ Challenges Faced / Resolution

Initially, I was confused by the `app` directory replacing the older `pages` approach in newer versions of Next.js. Reading the generated project files and experimenting with a new route clarified how the App Router works. I also spent a little time understanding the generated configuration files before modifying anything.

### 🎯 Next Steps

Tomorrow I'll explore the App Router in more detail, focusing on layouts, nested routes, and the overall routing workflow.

---

## 📅 Day 2 – Jul 2

**🏷️ Training Day:** Day 2 of 28
**📚 Topic:** App Router Fundamentals – File-based Routing, `page.tsx`, `layout.tsx`, and Nested Routes

---

### 🎯 Objective

Explore how the App Router organizes an application using the file system, understand the roles of `page.tsx` and `layout.tsx`, and learn how nested routes are structured in Next.js.

### 📌 Topics Covered

- File-based routing using the `app` directory and automatic route generation.
- Purpose and lifecycle of `page.tsx` as the entry point for a route.
- Using `layout.tsx` to share UI across multiple pages while preserving state.
- Creating nested routes by organizing folders within the `app` directory.
- Understanding layout inheritance and how child routes are rendered through the `children` prop.

### 💻 Hands-on / Practice

I built a small documentation-style application with a shared root layout containing a navigation bar and footer. I created routes such as `/docs`, `/docs/getting-started`, and `/docs/routing` to observe how nested layouts and pages work together without duplicating common UI.

### 📖 Key Learnings

- I now understand that routes are created entirely from the folder structure, eliminating the need for a separate routing configuration.
- I saw how `layout.tsx` persists across navigation, making it ideal for shared UI like sidebars and navigation menus.
- Building nested routes helped me understand how layouts can be composed hierarchically for different sections of an application.
- I found the App Router approach more structured than manually defining routes in traditional React applications.

### ⚡ Challenges Faced / Resolution

At first, I placed a page in an incorrect folder, which resulted in an unexpected route. Reviewing the folder hierarchy helped me understand that directory names directly determine URL paths. I also initially forgot to render the `children` prop in `layout.tsx`, causing nested pages not to appear until I corrected the layout component.

### 🎯 Next Steps

Tomorrow I'll explore navigation in the App Router, including the `Link` component, programmatic navigation with `useRouter`, tracking the current route using `usePathname`, and creating dynamic routes with `[id]`.

---

## 📅 Day 3 – Jul 3

**🏷️ Training Day:** Day 3 of 28
**📚 Topic:** Navigation – `Link` Component, `useRouter`, `usePathname`, and Dynamic Routes (`[id]`)

---

### 🎯 Objective

Learn how navigation works in the Next.js App Router by exploring declarative and programmatic navigation, tracking the active route, and building dynamic routes using URL parameters.

### 📌 Topics Covered

- Client-side navigation using the `Link` component.
- Programmatic navigation with the `useRouter` hook.
- Detecting the current route using `usePathname`.
- Creating dynamic routes using folders such as `app/products/[id]`.
- Accessing dynamic route parameters within route components.

### 💻 Hands-on / Practice

I built a small product catalog with a homepage listing products and individual product detail pages using dynamic routes (`/products/[id]`). I used the `Link` component to navigate between pages, highlighted the active navigation item with `usePathname`, and added a button that redirected users back to the homepage using `useRouter`.

### 📖 Key Learnings

- I understood that the `Link` component enables fast client-side navigation without triggering a full page refresh.
- I learned that `useRouter` is useful when navigation needs to happen in response to user actions rather than clickable links.
- Using `usePathname` made it straightforward to build navigation menus with active route highlighting.
- Dynamic routes felt intuitive because the folder structure directly mapped to URL parameters, making route organization predictable.

### ⚡ Challenges Faced / Resolution

Initially, I attempted to use `useRouter` inside a Server Component, which resulted in an error because it is a client-only hook. Adding the `"use client"` directive to the component resolved the issue. I also briefly confused static and dynamic route folder naming before realizing that route parameters must be enclosed in square brackets (e.g., `[id]`).

### 🎯 Next Steps

Tomorrow I'll explore React Server Components and Client Components, focusing on the `"use client"` boundary, rendering behavior, and choosing the appropriate component type for different scenarios.

---

## 📅 Day 4 – Jul 4

---

**🏷️ Training Day:** Day 4 of 28
**📚 Topic:** React Server Components vs Client Components – The Mental Model and the `"use client"` Boundary

---

### 🎯 Objective

Understand the differences between Server Components and Client Components in the Next.js App Router, when each should be used, and how the `"use client"` directive defines the client-side execution boundary.

### 📌 Topics Covered

- Default behavior of Server Components in the App Router.
- Purpose and implications of the `"use client"` directive.
- Deciding when to use Server Components versus Client Components.
- Limitations of Server Components (hooks, browser APIs, event handlers).
- Passing data from Server Components to Client Components while keeping the client bundle minimal.

### 💻 Hands-on / Practice

I built a simple dashboard where the page and data display were implemented as Server Components, while a search input and theme toggle were isolated into Client Components using the `"use client"` directive. This helped me observe how interactive features can be separated from server-rendered content.

### 📖 Key Learnings

- I realized that Server Components are the default in the App Router and are ideal for rendering data-driven UI without increasing the client-side JavaScript bundle.
- I now understand that the `"use client"` directive should only be added to components that genuinely require browser APIs, React state, or event handlers.
- Separating interactive elements into Client Components results in a cleaner architecture and better performance.
- Thinking in terms of a server-first rendering model feels different from traditional React but makes component responsibilities much clearer.

### ⚡ Challenges Faced / Resolution

I initially attempted to use `useState` inside a Server Component, which immediately produced an error. Moving the interactive logic into a dedicated Client Component marked with `"use client"` resolved the issue. I also learned to avoid adding the directive unnecessarily, as it increases the amount of JavaScript sent to the browser.

### 🎯 Next Steps

Tomorrow I'll explore data fetching in Server Components, including asynchronous components, the built-in `fetch` API, and creating loading states with `loading.tsx`.

---


## 📅 Day 5 – Jul 6

**🏷️ Training Day:** Day 5 of 28
**📚 Topic:** Data Fetching Basics – `fetch` in Server Components, Async Components, and Loading UI

---

### 🎯 Objective

Learn how data fetching works in the Next.js App Router by using asynchronous Server Components, the built-in `fetch` API, and route-level loading states to improve the user experience.

### 📌 Topics Covered

- Fetching data directly inside Server Components using the built-in `fetch` API.
- Creating asynchronous Server Components with `async`/`await`.
- Understanding how server-side data fetching differs from client-side fetching.
- Implementing route-level loading states with `loading.tsx`.
- Managing loading behavior while waiting for server-rendered data.

### 💻 Hands-on / Practice

I built a small blog page that fetched posts from a public API directly inside an async Server Component. I also created a `loading.tsx` file with a simple loading placeholder to observe how Next.js automatically displays a loading UI while the page data is being fetched.

### 📖 Key Learnings

- I found that data fetching feels much cleaner when it happens directly inside a Server Component instead of relying on client-side effects.
- Writing asynchronous page components made the data flow straightforward and reduced the amount of boilerplate code.
- I understood that `loading.tsx` provides a seamless loading experience without requiring additional state management.
- I now see why Next.js encourages server-first data fetching for better performance and improved initial page rendering.

### ⚡ Challenges Faced / Resolution

Initially, I expected `fetch` to behave exactly like it does in a browser environment, but I learned that Next.js extends it with framework-specific behavior on the server. I also forgot to place `loading.tsx` in the correct route segment, so the loading UI did not appear until I moved it to the appropriate directory.

### 🎯 Next Steps

Tomorrow I'll explore Next.js rendering strategies, comparing Server-Side Rendering (SSR), Static Site Generation (SSG), and Incremental Static Regeneration (ISR), and understand when each approach is the most appropriate.

---

## 📅 Day 6 – Jul 7

**🏷️ Training Day:** Day 6 of 28
**📚 Topic:** Rendering Strategies – SSR vs SSG vs ISR, When to Use Each

---

### 🎯 Objective

Understand the different rendering strategies available in Next.js and learn how to choose the most suitable approach based on data freshness, performance, and user experience.

### 📌 Topics Covered

- Differences between Server-Side Rendering (SSR), Static Site Generation (SSG), and Incremental Static Regeneration (ISR).
- How each rendering strategy affects performance, caching, and page generation.
- Identifying use cases where SSR, SSG, or ISR is the best fit.
- Configuring page revalidation for ISR.
- Trade-offs between build-time rendering and request-time rendering.

### 💻 Hands-on / Practice

I created a small demo application with three routes to compare rendering strategies. One page displayed static content generated at build time, another fetched frequently changing data using server-side rendering, and a third used ISR with a revalidation interval to observe how updated content was served without rebuilding the entire application.

### 📖 Key Learnings

- I now have a much clearer understanding of when each rendering strategy should be applied instead of treating them as interchangeable options.
- I found SSG to be ideal for content that rarely changes, while SSR is better suited for request-specific or frequently updated data.
- ISR provides a practical balance by allowing static pages to stay fast while periodically refreshing their content.
- Choosing the appropriate rendering strategy has a significant impact on application performance and scalability.

### ⚡ Challenges Faced / Resolution

Initially, I found it difficult to distinguish between SSR and ISR because both can serve fresh data. Experimenting with different revalidation intervals helped me understand that ISR serves cached static pages while regenerating them in the background. I also verified rendering behavior using browser developer tools and page refreshes to observe when content was regenerated.

### 🎯 Next Steps

Tomorrow I'll explore static route generation with `generateStaticParams` and learn how to use the Metadata API to implement SEO-friendly page titles, descriptions, and other metadata.

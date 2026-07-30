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

---

## 📅 Day 7 – Jul 8

**🏷️ Training Day:** Day 7 of 28
**📚 Topic:** Static Params & `generateStaticParams`, Metadata API (SEO Basics)

---

### 🎯 Objective

Learn how Next.js statically generates dynamic routes using `generateStaticParams` and understand how the Metadata API helps create SEO-friendly pages without relying on external libraries.

### 📌 Topics Covered

- Purpose of `generateStaticParams` for pre-rendering dynamic routes at build time.
- Using `generateStaticParams` with dynamic route segments such as `[slug]` or `[id]`.
- Static vs dynamic route generation and their impact on performance.
- Configuring page metadata using the built-in Metadata API.
- Adding page titles, descriptions, and Open Graph metadata for improved SEO.

### 💻 Hands-on / Practice

I built a simple blog application with dynamic post pages generated using `generateStaticParams`. Each post page included its own metadata, including a unique title and description, allowing me to verify that page-specific SEO information was automatically generated during rendering.

### 📖 Key Learnings

- I understood that `generateStaticParams` allows dynamic routes to be statically generated ahead of time, reducing request-time work and improving page performance.
- I found the Metadata API much cleaner than manually managing document head elements, especially since metadata is colocated with each route.
- I learned that metadata can be generated dynamically, making it easy to create SEO-friendly pages for content-driven applications.
- Combining static generation with route-specific metadata provides both better performance and improved discoverability by search engines.

### ⚡ Challenges Faced / Resolution

Initially, I expected every dynamic route to be generated automatically, but I realized that only the parameters returned by `generateStaticParams` are pre-rendered during the build. I also mistakenly defined metadata in the wrong file before moving it to the appropriate route segment, after which the page title and description updated correctly.

### 🎯 Next Steps

Tomorrow I'll explore Route Handlers in Next.js by building REST API endpoints using the `app/api` directory and handling different HTTP methods within the App Router.

---

## 📅 Day 8 – Jul 9

**🏷️ Training Day:** Day 8 of 28
**📚 Topic:** API Routes / Route Handlers – Building REST Endpoints Inside Next.js

---

### 🎯 Objective

Learn how to build RESTful API endpoints using Route Handlers in the Next.js App Router and understand how backend logic can be colocated within a Next.js application.

### 📌 Topics Covered

- Creating API endpoints using `route.ts` inside the `app/api` directory.
- Handling different HTTP methods such as `GET`, `POST`, `PUT`, and `DELETE`.
- Using `NextRequest` and `NextResponse` for processing requests and returning responses.
- Extracting query parameters, route parameters, and request bodies.
- Organizing Route Handlers for scalable API development within the App Router.

### 💻 Hands-on / Practice

I built a simple REST API for managing notes. The API supported listing notes with `GET`, creating new notes with `POST`, updating existing notes with `PUT`, and deleting notes with `DELETE`. I tested each endpoint using Postman and verified the responses by consuming the API from a simple Next.js page.

### 📖 Key Learnings

- I found Route Handlers intuitive because they follow standard REST principles while fitting naturally into the App Router's file-based structure.
- Using `NextRequest` and `NextResponse` made request parsing and response formatting straightforward without additional libraries.
- Since I already have backend experience, it was easy to relate Route Handlers to Express routes while appreciating the tighter integration within Next.js.
- Keeping frontend pages and lightweight backend endpoints in the same project can simplify development for full-stack applications.

### ⚡ Challenges Faced / Resolution

Initially, I attempted to create API files using the older `pages/api` convention before realizing that the App Router requires `route.ts` inside the `app/api` directory. I also forgot to return a `NextResponse` from one handler, which caused the request to fail until I corrected the response format.

### 🎯 Next Steps

Tomorrow I'll connect Route Handlers to a database, learning how to access backend data sources, perform database operations, and expose the results through Next.js API endpoints.

---

## 📅 Day 9 – Jul 10

**🏷️ Training Day:** Day 9 of 28
**📚 Topic:** Connecting Next.js to a Backend/Database – Calling a Database from Route Handlers

---

### 🎯 Objective

Understand how Route Handlers interact with a database and learn how to expose persistent data through Next.js API endpoints using a clean server-side architecture.

### 📌 Topics Covered

- Establishing database connections from Route Handlers.
- Performing CRUD operations within API endpoints.
- Structuring database access separately from route logic.
- Handling asynchronous database queries and error responses.
- Managing environment variables for secure database credentials.

### 💻 Hands-on / Practice

I connected a Next.js Route Handler to a PostgreSQL database using Prisma and implemented a simple task management API. The endpoints supported creating, retrieving, updating, and deleting tasks while validating requests and returning appropriate HTTP status codes. I verified the functionality using Postman before consuming the API from a Next.js page.

### 📖 Key Learnings

- I found that Route Handlers integrate naturally with existing backend patterns, making it easy to reuse concepts from my Node.js experience.
- Separating database logic from the route implementation made the code easier to maintain and extend.
- Environment variables provide a secure way to manage database connection details without exposing sensitive information.
- Combining Next.js Route Handlers with an ORM like Prisma results in a clean and type-safe backend workflow.

### ⚡ Challenges Faced / Resolution

Initially, I encountered a database connection issue because the environment variables were not loaded correctly after updating the `.env` file. Restarting the development server resolved the problem. I also ran into a Prisma client initialization error, which I fixed by reusing a single Prisma client instance instead of creating a new one for every request.

### 🎯 Next Steps

Tomorrow I'll explore Server Actions, learning how to perform data mutations and handle form submissions directly from Server Components without creating manual API endpoints.

---

## 📅 Day 10 – Jul 11

**🏷️ Training Day:** Day 10 of 28
**📚 Topic:** Server Actions – Mutations Without Manual API Calls, Form Handling

---

### 🎯 Objective

Understand how Server Actions simplify data mutations in the App Router by handling form submissions and server-side operations without creating separate REST API endpoints.

### 📌 Topics Covered

- Creating and using Server Actions with the `"use server"` directive.
- Connecting HTML forms directly to Server Actions.
- Performing create, update, and delete operations from Server Components.
- Passing `FormData` to Server Actions for server-side processing.
- Revalidating cached data after mutations using `revalidatePath`.

### 💻 Hands-on / Practice

I built a simple task management page where users could add and delete tasks through HTML forms connected directly to Server Actions. The submitted data was stored in a database using Prisma, and after each mutation I used `revalidatePath` to refresh the UI without manually fetching updated data.

### 📖 Key Learnings

- I found Server Actions to be a much cleaner approach for simple mutations because they eliminate the need to create separate API endpoints for every form submission.
- Handling `FormData` directly inside a Server Action made the data flow easier to follow and reduced boilerplate code.
- I understood how `revalidatePath` keeps server-rendered pages synchronized with the latest database changes after a mutation.
- Coming from an Express background, I appreciated how Next.js combines frontend and backend logic while still keeping responsibilities well organized.

### ⚡ Challenges Faced / Resolution

Initially, I forgot to mark the action with the `"use server"` directive, causing the form submission to fail. After adding the directive, the action executed correctly on the server. I also noticed that updated data was not reflected immediately until I added `revalidatePath` after the database operation.

### 🎯 Next Steps

Tomorrow I'll explore client-side state management in React, focusing on `useState`, `useEffect`, lifting state between components, and composing reusable component hierarchies.

---

## 📅 Day 11 – Jul 13

**🏷️ Training Day:** Day 11 of 28
**📚 Topic:** Client-side State – `useState`, `useEffect`, Lifting State, and Component Composition

---

### 🎯 Objective

Understand how client-side state is managed in React within a Next.js application and learn how to structure components so that state is shared efficiently and UI remains maintainable.

### 📌 Topics Covered

- Managing local component state using `useState`.
- Using `useEffect` for client-side side effects and synchronization.
- Lifting state to a common parent component for shared data.
- Building reusable UI through component composition.
- Identifying when state should remain local versus being shared across components.

### 💻 Hands-on / Practice

I built a small task management interface consisting of a task input, task list, and task counter. The parent component managed the shared state, while child components received data and callbacks through props. I also used `useEffect` to persist tasks to `localStorage` and restore them when the page was refreshed.

### 📖 Key Learnings

- I reinforced the idea that state should live in the closest common ancestor when multiple components need access to the same data.
- I found component composition to be a cleaner approach than creating large, monolithic components with mixed responsibilities.
- I better understood that `useEffect` is intended for synchronizing with external systems, such as browser storage, rather than for deriving state.
- Separating state management from presentation made the application easier to reason about and simplified future enhancements.

### ⚡ Challenges Faced / Resolution

Initially, I encountered unnecessary re-renders because I updated state inside an effect with an incorrect dependency array. Reviewing the dependency list and keeping only the required values resolved the issue. I also briefly duplicated state across components before lifting it to the parent, which eliminated synchronization problems.

### 🎯 Next Steps

Tomorrow I'll explore form handling in greater depth, including controlled inputs, client-side validation, and building robust forms using **React Hook Form** together with **Zod**.

---

## 📅 Day 12 – Jul 14

**🏷️ Training Day:** Day 12 of 28
**📚 Topic:** Forms in Depth – Controlled Inputs, Validation, and Integrating React Hook Form + Zod

---

### 🎯 Objective

Learn how to build scalable and type-safe forms in Next.js using React Hook Form for state management and Zod for schema-based validation.

### 📌 Topics Covered

- Managing controlled form inputs in React.
- Form state management using `react-hook-form`.
- Defining validation schemas with Zod.
- Integrating Zod with React Hook Form using `zodResolver`.
- Displaying validation errors and handling successful form submissions.

### 💻 Hands-on / Practice

I built a user registration form with fields for name, email, password, and confirm password. The form was managed using React Hook Form, while Zod handled schema validation, including password confirmation and email format checks. I displayed field-level validation messages and prevented submission until all validation rules passed.

### 📖 Key Learnings

- I found React Hook Form much more efficient than managing every input with individual `useState` hooks, especially as the form became larger.
- Using Zod allowed me to centralize validation rules in a single schema, making them easier to maintain and reuse.
- The integration between React Hook Form and Zod provided a clean, type-safe workflow with minimal boilerplate.
- Keeping validation logic separate from UI components made the form implementation more readable and easier to extend.

### ⚡ Challenges Faced / Resolution

Initially, my validation errors were not appearing because I forgot to connect the Zod schema through `zodResolver`. After configuring the resolver correctly, the validation worked as expected. I also encountered an issue with confirm password validation, which I resolved by refining the Zod schema to compare both password fields before submission.

### 🎯 Next Steps

Tomorrow I'll explore styling approaches in Next.js, comparing CSS Modules with Tailwind CSS and learning how to organize reusable, maintainable component styles.

---

## 📅 Day 13 – Jul 15

**🏷️ Training Day:** Day 13 of 28
**📚 Topic:** Styling in Next.js – CSS Modules, Tailwind CSS Setup and Usage

---

### 🎯 Objective

Learn the primary styling approaches available in Next.js, understand when to use CSS Modules versus Tailwind CSS, and build responsive, maintainable user interfaces using utility-first styling.

### 📌 Topics Covered

- Configuring Tailwind CSS in a Next.js project.
- Creating component-scoped styles with CSS Modules.
- Utility-first styling principles and responsive design using Tailwind.
- Combining global styles, CSS Modules, and Tailwind effectively.
- Organizing reusable styling patterns for scalable applications.

### 💻 Hands-on / Practice

I redesigned a small dashboard page by styling navigation cards, buttons, and a profile section. I used Tailwind CSS for layout, spacing, responsiveness, and typography, while applying CSS Modules to a reusable card component that required encapsulated styles and hover animations. I also implemented responsive layouts using Tailwind's breakpoint utilities.

### 📖 Key Learnings

- I found Tailwind CSS significantly faster for building responsive layouts because most styling can be completed directly within the component markup.
- CSS Modules remain useful when a component requires encapsulated styles or more complex selectors that would otherwise clutter the markup.
- Combining both approaches provides flexibility without sacrificing maintainability or consistency.
- Utility-first styling encourages reusable design patterns and minimizes context switching between JSX and separate stylesheet files.

### ⚡ Challenges Faced / Resolution

Initially, I mixed utility classes with custom CSS unnecessarily, making the components harder to maintain. After refactoring, I relied on Tailwind for layout and common styling while reserving CSS Modules only for component-specific effects. I also encountered missing styles after adding new utility classes, which was resolved by ensuring Tailwind scanned the correct project directories.

### 🎯 Next Steps

Tomorrow I'll explore component libraries such as **shadcn/ui**, learning how to integrate reusable UI components, customize them, and build a consistent design system for Next.js applications.

---

## 📅 Day 14 – Jul 16

**🏷️ Training Day:** Day 14 of 28
**📚 Topic:** Component Libraries – Using shadcn/ui and Building a Reusable UI Kit

---

### 🎯 Objective

Learn how to integrate a modern component library into a Next.js project, customize reusable UI components, and establish a consistent design system for scalable application development.

### 📌 Topics Covered

- Installing and configuring **shadcn/ui** in a Next.js application.
- Understanding how shadcn/ui generates editable component source files.
- Using reusable components such as Button, Card, Dialog, Input, and Badge.
- Customizing components with Tailwind CSS and design tokens.
- Organizing a reusable UI kit for consistent styling across the application.

### 💻 Hands-on / Practice

I set up **shadcn/ui** in a Next.js project and built a small admin dashboard using reusable components. The interface included navigation cards, a search bar, action buttons, modal dialogs, and form inputs. I customized component variants, adjusted spacing and colors with Tailwind CSS, and extracted commonly used UI elements into reusable components.

### 📖 Key Learnings

- I appreciated that shadcn/ui provides component source code instead of hiding implementation details behind a package, making customization much easier.
- Building a reusable UI kit reduced duplicated code and helped maintain a consistent design across different pages.
- Since the components are built with Tailwind CSS, extending or modifying their appearance felt straightforward.
- Treating UI components as reusable building blocks makes future development faster and keeps the codebase easier to maintain.

### ⚡ Challenges Faced / Resolution

Initially, I expected shadcn/ui components to behave like a traditional component library, but I realized they are copied directly into the project for full ownership and customization. I also encountered styling inconsistencies after modifying component variants, which I resolved by updating the shared utility classes instead of overriding styles individually.

### 🎯 Next Steps

Tomorrow I'll explore global state management using the React Context API, understand how shared application state is managed, and identify scenarios where Context alone is no longer sufficient.

---

## 📅 Day 15 – Jul 17

**🏷️ Training Day:** Day 15 of 28
**📚 Topic:** Global State Management – Context API Basics, When Context Isn't Enough

---

### 🎯 Objective

Understand how global state is managed in React applications using the Context API and learn when it is appropriate to use Context versus adopting a dedicated state management solution.

### 📌 Topics Covered

- Creating and consuming shared state with the React Context API.
- Using providers to make application-wide data accessible.
- Avoiding excessive prop drilling through Context.
- Understanding Context re-render behavior and performance considerations.
- Identifying scenarios where Context becomes difficult to scale and when dedicated state management libraries are more appropriate.

### 💻 Hands-on / Practice

I built a simple application with global theme and user preference management using the Context API. I created separate providers for theme and authentication state, wrapped the application with them, and consumed the shared state across multiple pages and reusable components without passing props through intermediate components.

### 📖 Key Learnings

- I found the Context API to be an effective solution for sharing application-wide data such as themes, authentication status, and user preferences.
- Separating different concerns into individual context providers made the application easier to organize and maintain.
- I realized that Context is intended for sharing state rather than replacing all local component state.
- I now understand that as application complexity and update frequency increase, dedicated state management libraries may offer better scalability and performance.

### ⚡ Challenges Faced / Resolution

Initially, I placed unrelated values inside a single context, which caused unnecessary component re-renders whenever any part of the state changed. Splitting the data into smaller, focused contexts resolved the issue and improved maintainability. I also ensured that custom hooks were used to simplify context consumption throughout the application.

### 🎯 Next Steps

Tomorrow I'll explore authentication fundamentals in Next.js, comparing session-based and token-based authentication, and learn how cookies are used to securely manage user sessions.

---

## 📅 Day 16 – Jul 18

**🏷️ Training Day:** Day 16 of 28
**📚 Topic:** Authentication Fundamentals – Session vs Token-Based Authentication, Cookies in Next.js

---

### 🎯 Objective

Understand the authentication mechanisms commonly used in Next.js applications, compare session-based and token-based authentication, and learn how cookies are securely managed within the App Router.

### 📌 Topics Covered

- Differences between session-based and JWT/token-based authentication.
- Using HTTP-only cookies for secure session management.
- Reading and setting cookies with the Next.js `cookies()` API.
- Authentication flow for login, protected routes, and logout.
- Security considerations such as cookie flags (`HttpOnly`, `Secure`, and `SameSite`).

### 💻 Hands-on / Practice

I implemented a basic authentication flow using Route Handlers. A login endpoint validated user credentials and stored a signed session token in an HTTP-only cookie. I then created a protected dashboard page that checked the cookie before rendering content and added a logout action that cleared the session cookie.

### 📖 Key Learnings

- I understood that session-based and token-based authentication solve similar problems but involve different trade-offs in storage, scalability, and validation.
- Using HTTP-only cookies improves security because authentication tokens remain inaccessible to client-side JavaScript.
- The `cookies()` API integrates naturally with Server Components and Route Handlers, making authentication checks straightforward.
- Authentication logic becomes easier to maintain when cookie handling, validation, and route protection are clearly separated.

### ⚡ Challenges Faced / Resolution

Initially, my authentication cookie was not available after login because I hadn't configured the cookie attributes correctly. After setting the appropriate options and verifying the response headers, the browser stored the cookie as expected. I also confirmed that protected routes validated the cookie on every request before rendering sensitive content.

### 🎯 Next Steps

Tomorrow I'll implement authentication end-to-end by integrating **Auth.js (NextAuth.js)** or building a custom JWT-based authentication flow, including login, session management, protected routes, and user sign-out.

---

## 📅 Day 17 – Jul 20

**🏷️ Training Day:** Day 17 of 28
**📚 Topic:** Implementing Authentication End-to-End – Auth.js (NextAuth.js) or a Custom JWT Flow

---

### 🎯 Objective

Implement a complete authentication flow in a Next.js application, from user login to protected routes, while understanding how Auth.js and custom JWT-based authentication fit into the App Router.

### 📌 Topics Covered

- Configuring authentication using Auth.js or a custom JWT implementation.
- Implementing login, logout, and session management.
- Protecting pages and Route Handlers based on authenticated user sessions.
- Storing authentication data securely using HTTP-only cookies.
- Accessing the authenticated user within Server Components and Route Handlers.

### 💻 Hands-on / Practice

I built a complete authentication flow for a small task management application. Users could register, log in, access a protected dashboard, and log out. I integrated Prisma for user persistence, securely hashed passwords before storage, validated credentials during login, and protected authenticated pages by verifying the active session before rendering user-specific content.

### 📖 Key Learnings

- I gained a much clearer understanding of how the different authentication pieces work together, from credential validation to session persistence and route protection.
- Auth.js simplifies many authentication concerns, while a custom JWT implementation offers greater flexibility when application requirements become more specialized.
- Authentication checks are most reliable when performed on the server rather than relying solely on client-side logic.
- Separating authentication, authorization, and database access keeps the overall implementation easier to maintain and extend.

### ⚡ Challenges Faced / Resolution

Initially, authenticated users were not remaining logged in after refreshing the page because the session configuration was incomplete. After reviewing the session and cookie settings, persistence worked correctly. I also encountered issues protecting both pages and API endpoints consistently, which I resolved by centralizing the session validation logic into reusable server-side utilities.

### 🎯 Next Steps

Tomorrow I'll explore Next.js Middleware, learning how to protect routes, perform redirects based on authentication state, and understand common use cases for Edge Middleware.

---

## 📅 Day 18 – Jul 21

**🏷️ Training Day:** Day 18 of 28
**📚 Topic:** Middleware – Route Protection, Redirects, and Edge Middleware Use Cases

---

### 🎯 Objective

Understand how Next.js Middleware intercepts incoming requests, enables route protection, performs redirects, and handles request processing at the edge before a route is rendered.

### 📌 Topics Covered

- Creating and configuring `middleware.ts` in a Next.js application.
- Protecting authenticated routes before page rendering.
- Redirecting users based on authentication or application state.
- Using the `matcher` configuration to control which routes execute middleware.
- Understanding common Edge Middleware use cases such as authentication, localization, and request rewriting.

### 💻 Hands-on / Practice

I implemented middleware for a dashboard application where protected routes checked for a valid authentication cookie before allowing access. Unauthenticated users were redirected to the login page, while authenticated users attempting to visit the login page were redirected to the dashboard. I also configured route matchers so middleware executed only for protected sections of the application.

### 📖 Key Learnings

- I learned that Middleware executes before a request reaches a page or Route Handler, making it ideal for centralized authentication and routing logic.
- Using route matchers helped avoid unnecessary middleware execution on public pages and static assets.
- I found that handling redirects in middleware keeps page components cleaner by moving access control into a single location.
- Edge Middleware provides fast request processing for scenarios like authentication, localization, and URL rewriting without duplicating logic across routes.

### ⚡ Challenges Faced / Resolution

Initially, my middleware executed on every request, including static assets, causing unnecessary processing. Configuring the `matcher` property restricted execution to only the required routes. I also encountered a redirect loop because authenticated and unauthenticated conditions overlapped, which I resolved by carefully ordering the redirect logic.

### 🎯 Next Steps

Tomorrow I'll explore error handling in Next.js, including route-level error boundaries with `error.tsx`, custom `not-found.tsx` pages, and effective `try/catch` patterns within Server Components.

---

## 📅 Day 19 – Jul 22

**🏷️ Training Day:** Day 19 of 28
**📚 Topic:** Error Handling – `error.tsx`, `not-found.tsx`, and `try/catch` Patterns in Server Components

---

### 🎯 Objective

Learn how Next.js handles application errors gracefully using route-level error boundaries, custom 404 pages, and robust error handling patterns inside Server Components.

### 📌 Topics Covered

- Creating route-level error boundaries with `error.tsx`.
- Displaying custom 404 pages using `not-found.tsx`.
- Using `notFound()` to handle missing resources.
- Implementing `try/catch` blocks for asynchronous operations in Server Components.
- Providing meaningful fallback UI while logging server-side errors.

### 💻 Hands-on / Practice

I enhanced a small blog application by adding an `error.tsx` file for unexpected runtime errors and a custom `not-found.tsx` page for invalid blog post IDs. I also wrapped database queries in `try/catch` blocks and used `notFound()` whenever a requested post did not exist, ensuring users always received an appropriate response instead of a generic error.

### 📖 Key Learnings

- I learned that `error.tsx` acts as a route-level error boundary, allowing individual sections of the application to recover from runtime failures without affecting the entire app.
- Using `notFound()` is much cleaner than manually checking for missing data and returning conditional UI.
- Handling exceptions inside Server Components helps prevent unexpected crashes and allows more meaningful error responses.
- Separating expected scenarios like missing data from unexpected runtime failures makes the application easier to maintain and debug.

### ⚡ Challenges Faced / Resolution

Initially, I expected `error.tsx` to catch every possible error, but I realized that expected conditions such as missing records should be handled with `notFound()` instead. I also forgot to expose the reset functionality in the error boundary, and after implementing the provided `reset()` callback, retrying failed renders worked as intended.

### 🎯 Next Steps

Tomorrow I'll explore Next.js caching and revalidation, learning how to control cached data using `revalidatePath`, `revalidateTag`, and the different caching options available with the built-in `fetch` API.

---

## 📅 Day 20 – Jul 23

**🏷️ Training Day:** Day 20 of 28
**📚 Topic:** Caching & Revalidation – `revalidatePath`, `revalidateTag`, and `fetch` Cache Options

---

### 🎯 Objective

Understand how Next.js caches server-rendered data and learn how to selectively invalidate cached content using revalidation APIs to keep applications both fast and up to date.

### 📌 Topics Covered

- Understanding the default caching behavior of the Next.js `fetch` API.
- Configuring cache strategies using options such as `force-cache` and `no-store`.
- Refreshing route data with `revalidatePath`.
- Invalidating tagged cache entries using `revalidateTag`.
- Choosing appropriate caching strategies for static, dynamic, and frequently updated data.

### 💻 Hands-on / Practice

I extended a simple blog application by fetching posts with different cache configurations to observe their behavior. After creating and updating posts through Server Actions, I used `revalidatePath` to refresh the blog listing and experimented with `revalidateTag` to invalidate only the affected cached content instead of refreshing the entire route.

### 📖 Key Learnings

- I learned that Next.js provides flexible caching controls without requiring manual cache management throughout the application.
- Using `revalidatePath` is effective when an entire route needs to display updated data after a mutation.
- I found `revalidateTag` more granular because it allows related cached resources to be refreshed without invalidating unrelated pages.
- Selecting the correct `fetch` cache option is important for balancing application performance with data freshness.

### ⚡ Challenges Faced / Resolution

Initially, updated content did not appear after a database mutation because the cached route was still being served. Calling `revalidatePath` after the mutation resolved the issue immediately. I also experimented with different `fetch` cache options to understand why some requests returned cached responses while others always fetched fresh data.

### 🎯 Next Steps

Tomorrow I'll explore image and font optimization in Next.js, learning how to use `next/image`, `next/font`, and other built-in performance features to improve loading speed and user experience.

---

## 📅 Day 21 – Jul 24

**🏷️ Training Day:** Day 21 of 28
**📚 Topic:** Image & Font Optimization – `next/image`, `next/font`, and Performance Basics

---

### 🎯 Objective

Learn how Next.js optimizes images and fonts using its built-in components and understand the performance benefits of reducing layout shifts, improving loading speed, and minimizing unnecessary network requests.

### 📌 Topics Covered

- Optimizing images with the `next/image` component.
- Using `next/font` to self-host and optimize web fonts.
- Preventing layout shifts by specifying image dimensions.
- Lazy loading, responsive image sizing, and automatic image optimization.
- Performance considerations such as Core Web Vitals and asset optimization.

### 💻 Hands-on / Practice

I optimized a landing page by replacing standard `<img>` tags with the `next/image` component and configured responsive image sizes for different screen widths. I also integrated a Google Font using `next/font`, applied it globally through the root layout, and compared the loading behavior before and after the optimizations using browser developer tools.

### 📖 Key Learnings

- I found that `next/image` provides responsive image optimization and lazy loading with very little configuration.
- Using `next/font` removes the need for external font requests, improving loading performance and reducing layout shifts.
- Defining image dimensions upfront helps create a more stable user experience by preventing unexpected layout movement.
- Small optimizations to assets can significantly improve overall application performance and Core Web Vitals.

### ⚡ Challenges Faced / Resolution

Initially, some external images failed to load because their domains were not included in the Next.js image configuration. After adding the required domains to the project configuration, image optimization worked correctly. I also noticed minor layout shifts until I specified proper image dimensions and responsive sizing.

### 🎯 Next Steps

Tomorrow I'll explore environment variables, project configuration, and scalable folder structures to organize a production-ready Next.js application while keeping sensitive configuration secure.

---

## 📅 Day 22 – Jul 25

**🏷️ Training Day:** Day 22 of 28
**📚 Topic:** Environment Variables, Configuration, and Project Structure for a Real App

---

### 🎯 Objective

Learn how to organize a production-ready Next.js application by managing environment variables securely, configuring project settings, and structuring the codebase for scalability and maintainability.

### 📌 Topics Covered

- Managing environment variables using `.env.local` and environment-specific configuration files.
- Understanding the difference between server-only variables and `NEXT_PUBLIC_` environment variables.
- Configuring application behavior through `next.config.ts`.
- Organizing folders for components, features, utilities, services, and shared libraries.
- Separating configuration, business logic, and reusable modules to improve project maintainability.

### 💻 Hands-on / Practice

I refactored a small Next.js project into a feature-based structure by separating API utilities, database logic, reusable UI components, hooks, and shared helper functions. I moved sensitive values such as database URLs and API keys into environment variables, updated the application to consume them correctly, and configured project settings through `next.config.ts` where required.

### 📖 Key Learnings

- I understood the importance of keeping sensitive credentials on the server and exposing only values that are intentionally public using the `NEXT_PUBLIC_` prefix.
- A well-organized project structure makes it easier to locate code, add new features, and collaborate with other developers.
- Centralizing configuration reduces duplication and keeps environment-specific changes isolated from application logic.
- Establishing consistent folder conventions early helps maintain code quality as the project grows.

### ⚡ Challenges Faced / Resolution

Initially, some environment variables were returning `undefined` because I forgot to restart the development server after modifying the `.env.local` file. I also accidentally exposed a server-only variable to the client before correcting it by removing the `NEXT_PUBLIC_` prefix and keeping the value accessible only on the server.

### 🎯 Next Steps

Tomorrow I'll explore testing React components in a Next.js application using **Jest** or **Vitest** together with **React Testing Library**, focusing on writing reliable unit tests for reusable UI components.

---



## 📅 Day 23 – Jul 27

**🏷️ Training Day:** Day 23 of 28
**📚 Topic:** Testing – Unit Testing Components with Jest/Vitest and React Testing Library

---

### 🎯 Objective

Learn how to write reliable unit tests for React components in a Next.js application using Jest or Vitest together with React Testing Library, ensuring UI behavior remains consistent as the application evolves.

### 📌 Topics Covered

- Setting up Jest/Vitest for a Next.js project.
- Writing component tests with React Testing Library.
- Querying elements using accessible selectors and user-focused assertions.
- Mocking functions, API calls, and Next.js-specific modules where required.
- Testing component rendering, user interactions, and conditional UI states.

### 💻 Hands-on / Practice

I configured Vitest with React Testing Library and wrote unit tests for reusable UI components, including a Button, Search Input, and Login Form. The tests verified rendering, user interactions, form validation messages, disabled button states, and callback execution. I also mocked a utility function and ensured the components behaved correctly under different input scenarios.

### 📖 Key Learnings

- I realized that effective component tests should focus on user-visible behavior rather than internal implementation details.
- React Testing Library encourages writing tests that closely resemble how users interact with the application, making them more maintainable.
- Mocking external dependencies keeps unit tests isolated and prevents unrelated services from affecting test results.
- Having automated tests provides confidence when refactoring reusable components or introducing new features.

### ⚡ Challenges Faced / Resolution

Initially, some tests failed because browser-specific APIs were unavailable in the test environment. Configuring the `jsdom` environment resolved the issue. I also encountered unreliable assertions when selecting elements by CSS classes, so I switched to accessible queries such as roles and labels, resulting in more stable and readable tests.

### 🎯 Next Steps

Tomorrow I'll take a deeper look at SEO in Next.js, covering the Metadata API, Open Graph tags, `sitemap.xml`, `robots.txt`, and structured data to improve search engine visibility and content sharing.

---

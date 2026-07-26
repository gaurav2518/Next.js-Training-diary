# Next.js Self-Training Diary

### One-Month Learning Log (28 Days)

**Date:** Jul 1
**Training Day:** Day 1 of 28
**Topic:** Introduction to Next.js – What it is, Why it exists over plain React, Project setup with `create-next-app`, and Folder structure overview

---

**Objective**
Understand what Next.js is, why it was created as a framework on top of React, and become familiar with creating a new project and navigating its default structure.

**Topics Covered**

- Purpose of Next.js and the problems it solves compared to a plain React SPA.
- Key built-in features such as file-based routing, server-side capabilities, and performance optimizations.
- Creating a new application using `create-next-app` and understanding the setup options.
- Overview of the default project structure (`app`, `public`, `components`, configuration files, etc.).
- Difference between framework conventions and a manually configured React project.

**Hands-on / Practice**
I initialized a new Next.js project using `create-next-app`, explored the generated folder structure, customized the homepage with a simple introduction, added a reusable `Header` component, and created an `about` route to understand how file-based routing works.

**Key Learnings**

- I understood that Next.js is not a replacement for React but a framework that builds on React with production-ready features already integrated.
- I noticed how much setup work is eliminated compared to configuring a React project from scratch.
- The App Router structure felt organized, and I could quickly identify where pages, layouts, and static assets belong.
- I realized that following the framework's conventions makes projects easier to scale and maintain.

**Challenges Faced / Resolution**
Initially, I was confused by the `app` directory replacing the older `pages` approach in newer versions of Next.js. Reading the generated project files and experimenting with a new route clarified how the App Router works. I also spent a little time understanding the generated configuration files before modifying anything.

**Next Steps**
Tomorrow I'll explore the App Router in more detail, focusing on layouts, nested routes, and the overall routing workflow.


**Date:** Jul 2
**Training Day:** Day 2 of 28
**Topic:** App Router Fundamentals – File-based Routing, `page.tsx`, `layout.tsx`, and Nested Routes

---

**Objective**
Explore how the App Router organizes an application using the file system, understand the roles of `page.tsx` and `layout.tsx`, and learn how nested routes are structured in Next.js.

**Topics Covered**

- File-based routing using the `app` directory and automatic route generation.
- Purpose and lifecycle of `page.tsx` as the entry point for a route.
- Using `layout.tsx` to share UI across multiple pages while preserving state.
- Creating nested routes by organizing folders within the `app` directory.
- Understanding layout inheritance and how child routes are rendered through the `children` prop.

**Hands-on / Practice**
I built a small documentation-style application with a shared root layout containing a navigation bar and footer. I created routes such as `/docs`, `/docs/getting-started`, and `/docs/routing` to observe how nested layouts and pages work together without duplicating common UI.

**Key Learnings**

- I now understand that routes are created entirely from the folder structure, eliminating the need for a separate routing configuration.
- I saw how `layout.tsx` persists across navigation, making it ideal for shared UI like sidebars and navigation menus.
- Building nested routes helped me understand how layouts can be composed hierarchically for different sections of an application.
- I found the App Router approach more structured than manually defining routes in traditional React applications.

**Challenges Faced / Resolution**
At first, I placed a page in an incorrect folder, which resulted in an unexpected route. Reviewing the folder hierarchy helped me understand that directory names directly determine URL paths. I also initially forgot to render the `children` prop in `layout.tsx`, causing nested pages not to appear until I corrected the layout component.

**Next Steps**
Tomorrow I'll explore navigation in the App Router, including the `Link` component, programmatic navigation with `useRouter`, tracking the current route using `usePathname`, and creating dynamic routes with `[id]`.

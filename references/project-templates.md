# Project Templates

When the onboarding interview reveals what the user is building, match against these templates to pre-populate their CodeSpring mind map. This gives them an instant starting point instead of a blank canvas.

## How to Match

Listen for keywords in the user's answer to "What are you trying to build?"

- "shop" / "store" / "sell" / "products" / "e-commerce" / "ecommerce" -> E-Commerce
- "book" / "appointment" / "schedule" / "calendar" / "salon" / "clinic" -> Booking Platform
- "crm" / "customers" / "leads" / "contacts" / "sales pipeline" -> CRM
- "dashboard" / "analytics" / "metrics" / "reports" / "internal" -> Internal Dashboard
- "automate" / "workflow" / "process" / "zapier" / "integration" -> Automation Tool
- "marketplace" / "two-sided" / "buyers and sellers" / "platform" -> Marketplace
- "saas" / "subscription" / "tool" / "app" (generic) -> SaaS Starter
- "content" / "blog" / "cms" / "publish" -> Content Platform
- "community" / "forum" / "members" / "social" -> Community Platform

If no match, don't force a template. Create features based on what they described.

---

## E-Commerce Store

```json
[
  {"title":"Product Catalog","description":"Browse and search products. Categories, filters, product pages with images, descriptions, and pricing."},
  {"title":"Shopping Cart","description":"Add items, update quantities, view cart summary. Persist across sessions."},
  {"title":"Checkout + Payments","description":"Shipping address, payment processing (Stripe), order confirmation. Handle errors gracefully."},
  {"title":"User Accounts","description":"Sign up, log in, view order history, save shipping addresses, manage profile."},
  {"title":"Order Management","description":"Admin view of all orders. Status tracking (pending, shipped, delivered). Email notifications."},
  {"title":"Inventory Management","description":"Track stock levels. Low stock alerts. Prevent overselling."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-stripe","title":"Stripe","description":"Payment processing"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"}]`

---

## Booking Platform

```json
[
  {"title":"Service Catalog","description":"List of bookable services with descriptions, durations, and pricing."},
  {"title":"Availability Calendar","description":"Show available time slots. Block out unavailable times. Handle timezone differences."},
  {"title":"Booking Flow","description":"Select service, pick date/time, confirm booking. Email confirmation sent automatically."},
  {"title":"User Accounts","description":"Sign up, log in, view upcoming and past bookings, cancel or reschedule."},
  {"title":"Admin Dashboard","description":"View all bookings, manage availability, see revenue. Daily/weekly overview."},
  {"title":"Notifications","description":"Email and/or SMS reminders before appointments. Cancellation notifications."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"},{"id":"tech-resend","title":"Resend","description":"Email notifications"}]`

---

## CRM (Customer Relationship Management)

```json
[
  {"title":"Contact Management","description":"Add, edit, search contacts. Store name, email, phone, company, notes. Tags for segmentation."},
  {"title":"Deal Pipeline","description":"Kanban board for tracking deals through stages (lead, qualified, proposal, negotiation, won/lost)."},
  {"title":"Activity Tracking","description":"Log calls, emails, meetings against contacts. Timeline view of all interactions."},
  {"title":"Task Management","description":"Create follow-up tasks linked to contacts or deals. Due dates and reminders."},
  {"title":"Dashboard + Reports","description":"Revenue pipeline, conversion rates, activity metrics. Filter by date range, rep, stage."},
  {"title":"User Accounts + Permissions","description":"Team login. Admin vs standard user roles. Assign contacts and deals to team members."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"},{"id":"tech-zustand","title":"Zustand","description":"State management"}]`

---

## Internal Dashboard

```json
[
  {"title":"Data Visualization","description":"Charts, graphs, and tables showing key business metrics. Real-time or near-real-time updates."},
  {"title":"Data Sources","description":"Connect to APIs, databases, or spreadsheets. Import and normalize data."},
  {"title":"Filters + Date Ranges","description":"Filter dashboard by date range, category, team, or custom dimensions."},
  {"title":"User Authentication","description":"Login with role-based access. Admin sees everything, team members see their data."},
  {"title":"Export + Reports","description":"Download data as CSV or PDF. Schedule automated email reports."},
  {"title":"Alerts + Notifications","description":"Set thresholds on metrics. Get notified when something needs attention."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-recharts","title":"Recharts","description":"Chart library"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"}]`

---

## Automation Tool

```json
[
  {"title":"Trigger Setup","description":"Define what starts the automation - schedule, webhook, form submission, email received, etc."},
  {"title":"Action Builder","description":"Define what happens - send email, update database, call API, generate document, notify someone."},
  {"title":"Workflow Editor","description":"Connect triggers to actions. If/then logic. Multiple steps in sequence."},
  {"title":"Run History","description":"Log of every automation run. Success/failure status. Error details for debugging."},
  {"title":"Dashboard","description":"Overview of all automations. Which are active, how many runs, success rates."},
  {"title":"User Accounts","description":"Login, manage automations, view run history. Team sharing optional."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"},{"id":"tech-bullmq","title":"BullMQ","description":"Job queue for scheduled tasks"}]`

---

## Marketplace

```json
[
  {"title":"Listing Management","description":"Sellers create listings with title, description, images, pricing. Edit and delete their own listings."},
  {"title":"Search + Discovery","description":"Browse by category. Search by keyword. Filters (price, location, rating). Sort options."},
  {"title":"User Accounts","description":"Buyer and seller accounts. Profile pages. Verification system."},
  {"title":"Transaction Flow","description":"Buyer purchases or requests. Payment escrow. Seller fulfills. Buyer confirms. Release payment."},
  {"title":"Reviews + Ratings","description":"Buyers rate sellers after transaction. Star ratings and written reviews. Trust score."},
  {"title":"Messaging","description":"In-app messaging between buyer and seller. Notification when new message received."},
  {"title":"Admin Panel","description":"Moderate listings and users. Resolve disputes. Platform analytics."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-stripe","title":"Stripe Connect","description":"Marketplace payments"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"},{"id":"tech-uploadthing","title":"UploadThing","description":"File/image uploads"}]`

---

## SaaS Starter (Generic)

```json
[
  {"title":"Authentication","description":"Sign up, log in, forgot password, email verification. OAuth options (Google, GitHub)."},
  {"title":"User Dashboard","description":"Main interface after login. Overview of their data, recent activity, quick actions."},
  {"title":"Core Feature","description":"The main thing your app does. This is the value - define it based on the user interview."},
  {"title":"Settings + Profile","description":"Update profile, change password, notification preferences, billing management."},
  {"title":"Billing + Subscriptions","description":"Stripe integration. Plan selection, upgrade/downgrade, invoices, cancel subscription."},
  {"title":"Admin Panel","description":"User management, subscription overview, usage metrics, support queue."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-stripe","title":"Stripe","description":"Billing"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"},{"id":"tech-nextauth","title":"NextAuth.js","description":"Authentication"}]`

---

## Content Platform / CMS

```json
[
  {"title":"Content Editor","description":"Rich text editor for creating posts/articles. Markdown or WYSIWYG. Image uploads."},
  {"title":"Content Organization","description":"Categories, tags, collections. Draft/published status. Scheduling for future publish."},
  {"title":"Public Display","description":"Blog/article listing page. Individual post pages. SEO-friendly URLs and meta tags."},
  {"title":"User Accounts","description":"Author accounts with profiles. Admin vs editor vs viewer roles."},
  {"title":"Comments + Engagement","description":"Comment system on posts. Like/bookmark functionality. Share buttons."},
  {"title":"Analytics","description":"View counts, popular posts, reader engagement metrics. Simple dashboard."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"},{"id":"tech-tiptap","title":"Tiptap","description":"Rich text editor"}]`

---

## Community Platform

```json
[
  {"title":"User Profiles","description":"Sign up, create profile with bio and avatar. Follow other members. Activity history."},
  {"title":"Discussion Threads","description":"Create posts, reply to posts, upvote/downvote. Threaded conversations. Rich text support."},
  {"title":"Categories + Spaces","description":"Organize discussions by topic. Public and private spaces. Moderation tools per space."},
  {"title":"Notifications","description":"New replies, mentions, follows. Email digest options. In-app notification center."},
  {"title":"Search","description":"Full-text search across posts and members. Filter by category, date, popularity."},
  {"title":"Moderation","description":"Report content, ban users, approve posts. Admin tools for community management."}
]
```

Tech stack: `[{"id":"tech-nextjs","title":"Next.js","description":"React framework"},{"id":"tech-prisma","title":"Prisma","description":"Database ORM"},{"id":"tech-postgres","title":"PostgreSQL","description":"Database"},{"id":"tech-tailwind","title":"Tailwind CSS","description":"Styling"},{"id":"tech-pusher","title":"Pusher","description":"Real-time notifications"}]`

---

## Boilerplate Feature Map

When the user installs the CodeSpring boilerplate (github.com/VolkisAI/codespring-boilerplate), add these as ALREADY BUILT features:

```json
[
  {"title":"Authentication (Built)","description":"Already included in boilerplate. NextAuth.js with email/password and OAuth providers. Login, signup, forgot password flows."},
  {"title":"Database Setup (Built)","description":"Already included in boilerplate. Prisma ORM with PostgreSQL. Schema ready with User model. Migrations configured."},
  {"title":"UI Framework (Built)","description":"Already included in boilerplate. Tailwind CSS with shadcn/ui components. Dark mode support. Responsive layout."},
  {"title":"Project Structure (Built)","description":"Already included in boilerplate. Next.js App Router. API routes. Middleware. Environment variables configured."}
]
```

Add notes to each: "This feature comes pre-built with the CodeSpring boilerplate. You don't need to build this - focus on your custom features instead."

# Next.js Features 🚀

## 1. Routing & Navigation
- **App Router & Pages Router**: `pages/index.js` (legacy) vs. `app/page.tsx` (new).
- **Dynamic Routes**: `pages/[id].js`, `app/products/[slug]/page.tsx`.
- **Middleware**: Handles authentication, redirects.
- **API Routes**: `pages/api/user.js` or `app/api/user/route.ts`.

## 2. Data Fetching & SSR
- **SSR**: `getServerSideProps()` fetches data per request.
- **SSG**: `getStaticProps()` pre-builds pages.
- **ISR**: `revalidate` updates static content dynamically.
- **Client Fetching**: `useEffect`, SWR, or React Query.
- **Server Actions** (Next.js 14+): Handle form submissions on the server.

## 3. Rendering Techniques
- **SSG**: Pre-rendered at build time.
- **SSR**: Generated on each request.
- **Streaming & Partial Rendering**: `React Server Components`.
- **CSR**: Uses `useEffect` for fetching on the client.

## 4. Styling
- **CSS Modules**: `import styles from './Home.module.css'`.
- **Tailwind CSS**: `className="text-center text-blue-500"`.
- **Styled Components**: `const Button = styled.button``color: blue;``;`.

## 5. State Management
- **Context API**: `createContext()` for global state.
- **Redux Toolkit**: `configureStore()`.
- **Zustand**: `create(set => ({ count: 0 }))`.

## 6. Authentication & Authorization
- **NextAuth.js**: `signIn('github')`.
- **JWT Auth**: Custom token-based authentication.

## 7. API & Backend Integration
- **REST API**: `axios.get('/api/user')`.
- **GraphQL**: `Apollo Client`.
- **Database**: `Prisma` for PostgreSQL/MongoDB.

## 8. Performance Optimization
- **Image Optimization**: `<Image src="/logo.png" width={200} height={100} />`.
- **Lazy Loading**: `React.lazy(() => import('./Component'))`.
- **Route Prefetching**: Built-in for faster navigation.

## 9. Deployment & Hosting
- **Vercel** (official host) or **AWS, Firebase**.
- **Docker Deployment**: `Dockerfile` setup.

## 10. Internationalization (i18n)
- **next-intl** or **i18next** for multi-language support.

## 11. PWA & Offline Support
- **Next.js PWA Plugin**: Adds offline capabilities.

## 12. Real-time Functionality
- **WebSockets**: `Socket.io` for real-time updates.
- **GraphQL Subscriptions**: Real-time GraphQL data.

### Which features are you planning to use? 🚀

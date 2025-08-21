# Resource Explorer - Pokémon Edition

A polished React application that explores the PokéAPI with advanced search, filtering, and favorites functionality. Built with Next.js, TypeScript, and Tailwind CSS.

## Features

### ✅ Must-Have Requirements (All Implemented)

1. **Project Setup**

   - React with Next.js and TypeScript
   - Sensible file structure with clear component boundaries
   - Modern development setup with ESLint and Tailwind CSS

2. **Data List + Detail View**

   - Paginated list view with 20 items per page
   - Individual Pokémon detail pages at `/pokemon/:id`
   - Responsive grid layout with proper navigation

3. **Search, Filter, Sort**

   - Debounced search (300ms) bound to URL parameters
   - Type filtering with dropdown selection
   - Sort by name or ID
   - URL reflects all state (shareable and reload-safe)

4. **Favorites**

   - Toggle favorites from both list and detail views
   - Persisted in localStorage
   - Favorites filter to show only favorited Pokémon

5. **Data Fetching and State**
   - Loading skeletons and error boundaries
   - Request cancellation using AbortController
   - React Query for caching and background refetch

### 🌟 Nice-to-Have Features (All Implemented)

- **Client Caching**: React Query provides intelligent caching
- **Theme Toggle**: Light/dark/system theme with persistent preference
- **Code Splitting**: Detail routes are code-split automatically
- **Accessibility**: Proper ARIA labels, focus management, and keyboard navigation
- **Optimistic UI**: Immediate feedback for favorite toggles
- **Error Handling**: Graceful error states with retry functionality

## Tech Stack

- **Framework**: Next.js 15 with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **State Management**: React Query (TanStack Query)
- **Data Fetching**: Custom API service with AbortController
- **Theme**: next-themes for dark/light mode
- **Icons**: Lucide React
- **Utilities**: clsx, tailwind-merge

## Project Structure

```
src/
├── app/                    # Next.js App Router
│   ├── layout.tsx         # Root layout with providers
│   ├── page.tsx           # Main explorer page
│   └── pokemon/[id]/      # Dynamic detail pages
├── components/            # Reusable UI components
│   ├── header.tsx         # App header with theme toggle
│   ├── search.tsx         # Debounced search input
│   ├── filters.tsx        # Filter and sort controls
│   ├── pokemon-card.tsx   # Individual Pokémon card
│   ├── loading-skeleton.tsx # Loading states
│   ├── error-boundary.tsx # Error handling
│   └── theme-toggle.tsx   # Theme switcher
├── hooks/                 # Custom React hooks
│   ├── use-pokemon.ts     # React Query hooks for API
│   └── use-url-state.ts   # URL state management
├── lib/                   # Utilities and services
│   ├── api.ts            # PokéAPI service
│   ├── favorites.ts      # localStorage favorites
│   └── utils.ts          # Utility functions
└── components/           # Provider components
    └── providers.tsx     # React Query and theme providers
```

## Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn

### Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd resource-explorer
```

2. Install dependencies:

```bash
npm install
```

3. Start the development server:

```bash
npm run dev
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser.

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

## API Integration

The app integrates with the [PokéAPI](https://pokeapi.co/) to fetch:

- **Pokémon List**: Paginated list with search capabilities
- **Individual Pokémon**: Detailed information including stats, abilities, and sprites
- **Types**: For filtering functionality

### Key API Features

- **Request Cancellation**: Uses AbortController to cancel in-flight requests
- **Error Handling**: Graceful fallbacks for API failures
- **Caching**: React Query provides intelligent caching and background updates
- **Optimistic Updates**: Immediate UI feedback for user actions

## State Management

### URL State

All search, filter, sort, and pagination state is managed in the URL:

- `?q=search` - Search query
- `?type=fire` - Type filter
- `?sort=name` - Sort order
- `?page=2` - Current page
- `?favorites=true` - Show only favorites

### Local Storage

Favorites are persisted in localStorage for a seamless user experience.

## Performance Optimizations

- **Code Splitting**: Automatic code splitting for detail routes
- **Image Optimization**: Next.js Image component with proper sizing
- **Request Deduplication**: React Query prevents duplicate requests
- **Skeleton Loading**: Smooth loading states for better UX
- **Debounced Search**: Prevents excessive API calls during typing

## Accessibility Features

- **Keyboard Navigation**: Full keyboard support for all interactive elements
- **Screen Reader Support**: Proper ARIA labels and semantic HTML
- **Focus Management**: Clear focus indicators and logical tab order
- **Color Contrast**: High contrast ratios for text and interactive elements
- **Reduced Motion**: Respects user's motion preferences

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers

## Deployment

The app can be deployed to any platform that supports Next.js:

- **Vercel** (recommended)
- **Netlify**
- **Railway**
- **Self-hosted**

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

MIT License - see LICENSE file for details.

## Acknowledgments

- [PokéAPI](https://pokeapi.co/) for providing the Pokémon data
- [Next.js](https://nextjs.org/) for the amazing React framework
- [Tailwind CSS](https://tailwindcss.com/) for the utility-first CSS framework
- [React Query](https://tanstack.com/query) for data fetching and caching

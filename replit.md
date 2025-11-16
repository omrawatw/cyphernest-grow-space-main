# Meme Battle Platform

A vibrant, interactive web application where users can upload, share, and battle with memes. Built with React, TypeScript, and Express.

## Recent Changes (November 15, 2025)

### Complete MVP Implementation
- ✅ Simple name-based authentication system
- ✅ Meme feed with real-time updates
- ✅ Image upload with drag-and-drop support
- ✅ Caption editing functionality
- ✅ Like/unlike system with live counts
- ✅ Comment system with threaded discussions
- ✅ Full CRUD operations for user-owned memes
- ✅ Beautiful, responsive UI following design guidelines
- ✅ All end-to-end tests passing

## Project Architecture

### Frontend
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side navigation
- **State Management**: TanStack Query v5 for server state
- **UI Components**: Shadcn UI with Radix primitives
- **Styling**: Tailwind CSS with custom design tokens
- **Fonts**: Inter (body) + Space Grotesk (display)

### Backend
- **Server**: Express.js
- **Storage**: In-memory storage (MemStorage)
- **File Upload**: Multer for multipart/form-data handling
- **Validation**: Zod schemas with Drizzle types

### Data Models
- **Users**: id, username
- **Memes**: id, userId, imageUrl, caption, createdAt
- **Likes**: id, memeId, userId, createdAt
- **Comments**: id, memeId, userId, text, createdAt

## Key Features

### Authentication
- Simple username-only login
- No passwords required
- User creation on first login
- Session stored in localStorage

### Meme Management
- Upload images (JPG, PNG, GIF, WebP, max 10MB)
- Add and edit captions (max 280 characters)
- Delete owned memes
- View all memes in chronological feed

### Social Interactions
- Like/unlike any meme
- Real-time like counts
- Add comments to any meme
- View all comments with author names
- Expandable comment threads

### User Experience
- Responsive design (mobile-first)
- Beautiful loading states with skeletons
- Toast notifications for all actions
- Empty state guidance
- Smooth animations and interactions

## API Endpoints

### Authentication
- `POST /api/auth/login` - Login with username

### Memes
- `GET /api/memes?userId={userId}` - Get all memes with metadata
- `POST /api/memes` - Upload meme (FormData)
- `PATCH /api/memes/:id` - Update caption
- `DELETE /api/memes/:id` - Delete meme

### Likes
- `POST /api/likes` - Like a meme
- `DELETE /api/likes/:memeId?userId={userId}` - Unlike a meme

### Comments
- `GET /api/comments` - Get all comments grouped by meme
- `POST /api/comments` - Add comment

## Design System

### Colors (Purple Theme)
- **Primary**: HSL(280, 85%, 45%) - Vibrant purple
- **Background**: White (light mode) / HSL(0, 0%, 6%) (dark mode)
- **Card**: HSL(0, 0%, 98%) / HSL(0, 0%, 8%)

### Typography
- **Display**: Space Grotesk (headings, usernames)
- **Body**: Inter (content, UI text)
- **Hierarchy**: Clear size and weight differentiation

### Spacing
- Small: 0.5rem (2 units)
- Medium: 1rem (4 units)
- Large: 2rem (8 units)

## File Structure

```
client/
├── src/
│   ├── components/
│   │   ├── navigation.tsx - Top navigation bar
│   │   ├── meme-card.tsx - Individual meme display
│   │   ├── upload-modal.tsx - Meme upload dialog
│   │   ├── comment-section.tsx - Comment display and input
│   │   └── ui/ - Shadcn component library
│   ├── pages/
│   │   ├── login.tsx - Login page
│   │   ├── home.tsx - Main feed page
│   │   └── not-found.tsx - 404 page
│   ├── lib/
│   │   ├── queryClient.ts - TanStack Query setup
│   │   └── utils.ts - Helper functions
│   └── App.tsx - Main app component
server/
├── routes.ts - API endpoint definitions
├── storage.ts - In-memory data storage
└── index.ts - Express server setup
shared/
└── schema.ts - Shared TypeScript types and Zod schemas
```

## Running the Application

The application runs automatically on Replit:
```bash
npm run dev
```

This starts:
- Express server on port 5000
- Vite dev server (HMR enabled)
- Serves both frontend and backend on the same port

## User Preferences

None specified yet.

## Testing

All core user journeys have been tested end-to-end:
- ✅ Login flow
- ✅ Meme upload with image and caption
- ✅ Like/unlike functionality
- ✅ Comment system
- ✅ Edit caption
- ✅ Delete meme
- ✅ Logout flow

## Future Enhancements

Potential features for next iteration:
- User profiles with uploaded meme history
- Head-to-head meme voting/battles
- Meme categories and filtering
- Leaderboard for top creators
- Direct meme sharing links
- Social media integration
- Real-time notifications
- Image editing tools (text overlay, filters)

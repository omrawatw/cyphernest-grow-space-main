# Meme Battle Platform - Design Guidelines

## Design Approach
**Reference-Based**: Drawing inspiration from Instagram's visual feed patterns, Twitter's engagement mechanics, and Reddit's community interaction model, adapted for meme-focused content with competitive elements.

## Core Design Principles
1. **Content-First**: Memes dominate the visual hierarchy
2. **Frictionless Interaction**: One-click likes, inline commenting
3. **Playful Energy**: Energetic spacing and bold typography that matches meme culture
4. **Mobile-Optimized**: Vertical scrolling feed with touch-friendly targets

---

## Typography System

**Primary Font**: Inter (via Google Fonts CDN)
**Secondary Font**: Space Grotesk (for headings/usernames)

Hierarchy:
- Page Title/Branding: 2xl (24px), Bold, Space Grotesk
- Usernames: base (16px), Semibold, Space Grotesk
- Captions: base (16px), Regular, Inter
- Timestamps: sm (14px), Regular, Inter
- Buttons/CTAs: base (16px), Medium, Inter
- Comment text: sm (14px), Regular, Inter
- Like counts: xs (12px), Semibold, Inter

---

## Layout System

**Spacing Units**: Tailwind units of 2, 3, 4, 6, 8
- Micro spacing (buttons, form inputs): 2-3
- Component internal spacing: 4-6
- Section spacing: 8

**Container Strategy**:
- Main feed: max-w-2xl mx-auto (optimal for meme viewing)
- Upload modal: max-w-4xl (space for editor)
- Single column feed on all breakpoints (meme-focused)

---

## Component Library

### 1. Login Screen
- Centered card (max-w-md)
- Large input field for name entry
- Bold "Enter Battle" CTA button
- Subtle tagline above: "Join the Meme Battle"

### 2. Navigation Bar (Sticky Top)
- Logo/Title left
- Upload button (prominent) center-right
- Username indicator right
- Height: 16 (64px)
- Icons: Heroicons (outline style)

### 3. Upload Interface (Modal/Overlay)
Two-step design:
- **Step 1**: Image upload dropzone with preview
- **Step 2**: Edit interface with:
  - Image preview (max 512px square)
  - Caption textarea (max 280 chars, Instagram-style)
  - Text overlay controls (position, size, style)
  - "Post to Battle" CTA

### 4. Meme Card (Feed Item)
Structure (top to bottom):
- Header: Avatar placeholder + Username + Timestamp (h-12)
- Meme Image: Full-width, auto-height (max-h-screen for very tall images)
- Engagement Bar: Like button + count, Comment button + count (h-12, space-x-6)
- Caption: Padded text below engagement
- Comment Section: Expandable, shows latest 2 initially

Card spacing: p-4, mb-6
Border: Subtle rounded corners (rounded-lg)

### 5. Like Button
- Heart icon (Heroicons)
- Animates on click (scale + fill state change)
- Count displays adjacent
- Size: 6 (24px icon)

### 6. Comment System
- Input: Inline below each meme with "Add comment..." placeholder
- Display: Username + comment text, stacked vertically
- Show "View all X comments" if >2 comments
- Individual comments: py-2 spacing

### 7. Edit Functionality
- Three-dot menu on user's own memes
- Dropdown: "Edit caption" | "Delete"
- Edit opens same caption textarea inline

---

## Interaction Patterns

**Upload Flow**:
1. Click floating upload button → Modal opens
2. Drag/drop or click to upload → Preview appears
3. Add caption + text overlays → Live preview updates
4. Click "Post" → Modal closes, meme appears at feed top

**Like Interaction**: Single tap/click toggles, instant visual feedback

**Comment Interaction**: 
- Click comment icon → Input focuses
- Type + Enter to submit → Appears immediately
- Click "View all" → Expands full thread

---

## Iconography
**Library**: Heroicons (outline style)
**Key Icons**:
- Upload: cloud-arrow-up
- Like: heart (outline/solid states)
- Comment: chat-bubble-left
- Menu: ellipsis-vertical
- Edit: pencil
- Delete: trash

---

## Images Section

**No hero image** - This is an application interface, not a landing page.

**Required Images**:
- User avatar placeholders: 32px circles with initials on gradient backgrounds
- Meme uploads: User-generated content (center-cropped to fit container)
- Empty state illustration: Playful "No memes yet" graphic when feed is empty

**Image Treatment**:
- Meme images: Maintain aspect ratio, max-width 100%
- Sharp corners for meme content (authentic feel)
- Rounded corners for UI elements (avatars, cards)

---

## Responsive Behavior

- Single column throughout (mobile-first)
- Upload button: Fixed position on mobile (bottom-right FAB)
- Navigation: Collapses username to icon on small screens
- Meme cards: Full-width below 640px, max-w-2xl above

---

## Accessibility
- All interactive elements: min 44px touch targets
- Form inputs: Visible labels + placeholder text
- Icon buttons: aria-labels for screen readers
- Keyboard navigation: Tab through feed, Enter to like/comment
- Focus indicators: Visible ring on all interactive elements
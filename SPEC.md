# Email AI Dashboard - Product Specification

## Product Overview
**Name:** MailSight - AI Email Dashboard
**Platform:** Web app (primary), Mobile app (secondary)
**Target:** Everyday consumers
**Core Value:** Transform email data into actionable insights through AI-powered dashboards

---

## Dashboard Types

### 1. Spending & Budgeting Dashboard
- Monthly spending breakdown by category
- Receipt parsing from purchase confirmations
- Spending trends over time (charts)
- Upcoming bills prediction
- Budget alerts and recommendations

### 2. Subscriptions Dashboard
- Active subscriptions list with costs
- Renewal dates calendar
- Cancel/manage subscription links
- Annual/monthly cost summary
- Unused subscription detection

### 3. Travel Dashboard
- Upcoming trips from booking confirmations
- Flight/hotel/itinerary details
- Boarding passes attachments
- Travel expense tracking
- Destination weather preview

### 4. Calendar Dashboard
- Event extraction from confirmation emails
- Upcoming events timeline
- RSVP tracking
- Calendar sync (Google Calendar, Apple Calendar)
- Smart reminders

---

## User Flows

### Email Connection Flow
1. **Welcome Screen** → "Connect Your Email"
2. **Provider Selection** → Gmail, Outlook, Yahoo, iCloud, Other IMAP
3. **OAuth/IMAP Authentication**
4. **Permission Request** → Read emails, Send on your behalf (optional)
5. **Processing Screen** → "Analyzing your emails..."
6. **Dashboard Home** → Main dashboard view

### Onboarding Journey
1. Welcome/Value proposition
2. Email connection (OAuth)
3. Permission grants
4. AI processing animation
5. Dashboard reveal with tour
6. Customize preferences

---

## Screen Requirements

### Screens to Build
1. **Landing/Welcome** - Value prop + Connect CTA
2. **Email Provider Selection** - Grid of providers
3. **Processing/Loading** - Animated AI parsing visualization
4. **Dashboard Home** - Overview with cards for each dashboard type
5. **Spending Dashboard** - Detailed financial view
6. **Subscriptions Dashboard** - Subscription management
7. **Travel Dashboard** - Trip details
8. **Calendar Dashboard** - Event timeline
9. **Settings** - Account, preferences, disconnect

---

## UI/UX Requirements

### Visual Style
- Clean, modern, card-based design
- Subtle gradients and shadows
- Smooth transitions between views
- Data visualizations (charts, graphs)

### Interactions
- Clickable navigation between dashboards
- Animated data loading
- Interactive charts
- Responsive design (desktop + mobile)

### Color Palette
- Primary: Deep Blue (#1a73e8)
- Secondary: Soft Purple (#7c4dff)
- Accent: Coral (#ff6b6b)
- Background: Light Gray (#f8f9fa)
- Cards: White (#ffffff)
- Text: Dark Gray (#202124)

---

## Technical Implementation

### Structure
- Single HTML file with embedded CSS/JS
- Tab-based navigation between views
- CSS Grid/Flexbox for layouts
- Chart.js for data visualizations
- Smooth scroll and fade transitions

### Mobile Adaptation
- Responsive breakpoints at 768px
- Stacked cards on mobile
- Touch-friendly tap targets

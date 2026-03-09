# Email Dashboard - User Pathways Documentation

This document comprehensively maps all user flows in the MailSight email dashboard prototype.

---

## Table of Contents
1. [Landing → Connect → Provider → Dashboard](#1-landing--connect--provider--dashboard)
2. [Dashboard → Home → Card Clicks](#2-dashboard--home--card-clicks)
3. [Dashboard → Spending](#3-dashboard--spending)
4. [Dashboard → Subscriptions](#4-dashboard--subscriptions)
5. [Dashboard → Travel](#5-dashboard--travel)
6. [Dashboard → Calendar](#6-dashboard--calendar)
7. [Dashboard → Settings](#7-dashboard--settings)
8. [Dashboard → Create Custom Dashboard](#8-dashboard--create-custom-dashboard)
9. [Mobile: Hamburger Menu](#9-mobile-hamburger-menu)

---

## 1. Landing → Connect → [Provider] → Dashboard

### Flow Overview
```
Landing Screen → Connect Button → Provider Selection → Processing → Dashboard
```

### Pathway Details

#### 1.1 Landing Screen
- **What happens**: User lands on the welcome/landing screen
- **UI Elements**:
  - Logo (📧 emoji)
  - Title: "MailSight"
  - Description text explaining the service
  - "Connect Your Email" button (`.btn`)
- **Data/State Changes**: None initially

#### 1.2 Provider Selection Screen
- **What happens**: After clicking "Connect Your Email", the provider selection modal appears
- **UI Elements**:
  - Title: "Choose Your Provider"
  - 4 provider buttons in a grid (`.provider-grid`):
    - Gmail (📬)
    - Outlook (📨)
    - Yahoo (📯)
    - iCloud (☁️)
  - "Back" button to return to landing
- **Data/State Changes**: None

#### 1.3 Processing Screen
- **What happens**: After selecting a provider, shows animated processing screen for ~3 seconds
- **UI Elements**:
  - Animated scanner icon with spinning rings
  - Title: "Analyzing Your Emails"
  - Progress bar with animated fill
  - List of email items being processed:
    - receipt → Processing...
    - booking → Processing...
    - event → Done
    - subscription → Done
- **Data/State Changes**: None (simulated)

#### 1.4 Dashboard View (Post-Connect)
- **What happens**: After processing completes, user lands on the main dashboard
- **UI Elements**:
  - Sidebar (visible on desktop)
  - Home view with summary cards
  - User info in sidebar footer (Avatar "RN", name, email)
- **State Changes**:
  - Screen switches to `#dashboard-view`
  - `showDashboardHome()` is called

### Provider-Specific Notes
| Provider | Button | Flow |
|----------|--------|------|
| Gmail | 📬 Gmail | `connectProvider('Gmail')` |
| Outlook | 📨 Outlook | `connectProvider('Outlook')` |
| Yahoo | 📯 Yahoo | `connectProvider('Yahoo')` |
| iCloud | ☁️ iCloud | `connectProvider('iCloud')` |

All providers follow identical flow (simulation only, no real authentication).

---

## 2. Dashboard → Home → Card Clicks

### Flow Overview
```
Dashboard Home → Click Summary Card → Detail View
```

### Pathway Details

#### 2.1 Home Screen (Default Dashboard View)
- **What happens**: User sees summary overview with 4 clickable cards
- **UI Elements**:
  - Header: "Your Dashboard" title
  - "+ Create Dashboard" button
  - 4 Summary Cards (`.dash-card`):
    1. **Total Spending**: $2,847 (💳 icon, green gradient)
    2. **Active Subscriptions**: 8 (🔄 icon, purple gradient)
    3. **Upcoming Trips**: 2 (✈️ icon, orange gradient)
    4. **This Month**: 12 (📅 icon, pink gradient)
  - Custom Dashboards section (if any exist)
- **Data/State Changes**: None initially

#### 2.2 Card Click Actions
| Card | Click Action | Destination |
|------|--------------|-------------|
| Total Spending | `showDetail('spending')` | Spending Detail View |
| Active Subscriptions | `showDetail('subscriptions')` | Subscriptions Detail View |
| Upcoming Trips | `showDetail('travel')` | Travel Detail View |
| This Month | `showDetail('calendar')` | Calendar Detail View |

#### 2.3 Navigation via Sidebar
- **UI Elements**: Sidebar nav items (`.nav-item`)
  - Home 🏠
  - Spending 💳
  - Subscriptions 🔄
  - Travel ✈️
  - Calendar 📅
  - Settings ⚙️
- **Behavior**: Clicking any nav item calls `showDetail(<section>)` or `showDashboardHome()` for Home

---

## 3. Dashboard → Spending

### Flow Overview
```
Spending Detail → View Stats → Interact with Chart → Expand Categories
```

### Pathway Details

#### 3.1 Spending Detail View
- **What happens**: Shows spending analytics with stats, chart, and category breakdown
- **UI Elements**:
  - Back button ("← Back")
  - Title: "Spending"
  - Stats Row (`.stats-row`):
    - This Month: $2,847
    - Last Month: $3,124
    - Avg. Daily: $95
    - Budget: $3,500
  - Chart container with doughnut chart (`.chart-container`)
  - Categories section (`.list-section`)

#### 3.2 Chart Interaction
- **What happens**: Click on chart segments to see category details
- **UI Elements**: Chart.js doughnut chart showing:
  - Food & Dining: $847 (orange)
  - Shopping: $623 (pink)
  - Transportation: $412 (purple)
  - Entertainment: $358 (green)
  - Utilities: $607 (violet)
- **Interactions**:
  - **Click on segment**: 
    1. Expands category purchases list (collapses others)
    2. Shows toast notification: `{Category}: $X (Y purchases)`
    3. Cursor changes to pointer to indicate clickability
- **Data/State Changes**: 
  - `expandedIndex` tracks which category is expanded
  - `showToast()` creates temporary notification element

#### 3.3 Category List Interactions
- **What happens**: Each category can be clicked to expand/collapse purchases
- **UI Elements**: Category items (`.category-item`) with:
  - Icon with category color
  - Category name
  - Number of purchases
  - Total amount
- **Interactions**:
  - **Click category**: 
    1. Toggles `.active` class
    2. Expands/collapses `.top-purchases` div
    3. Shows itemized purchase list
- **Categories**:
  | Category | Purchases | Amount |
  |----------|-----------|--------|
  | Food & Dining | Whole Foods, Chipotle, DoorDash | $847 |
  | Shopping | Amazon, Target | $623 |
  | Transportation | Uber, Gas | $412 |
  | Entertainment | Netflix, Spotify | $358 |
  | Utilities | Electric, Internet | $607 |

#### 3.4 Purchase Item Details
- **What happens**: When category is expanded, shows individual purchases
- **UI Elements**: `.purchase-item` elements showing:
  - Merchant name
  - Amount
- **Interactions**: None (display only)

---

## 4. Dashboard → Subscriptions

### Flow Overview
```
Subscriptions Detail → View List → Cancel Subscription
```

### Pathway Details

#### 4.1 Subscriptions Detail View
- **What happens**: Shows all subscription services with costs
- **UI Elements**:
  - Back button ("← Back")
  - Title: "Subscriptions"
  - Stats Row:
    - Monthly: $127
    - Yearly: $1,524
    - Active: 8
    - Unused: 2
  - Active Subscriptions list

#### 4.2 Subscription List Items
- **What happens**: Displays each subscription with status and actions
- **UI Elements**: Each `.list-item` contains:
  - First letter icon (colored)
  - Subscription name
  - Next billing date detail
  - "Active" badge (green)
  - "Cancel" button
- **Subscriptions**:
  | Name | Price | Period | Next Billing |
  |------|-------|--------|--------------|
  | Netflix | $15 | monthly | Mar 15 |
  | Spotify | $10 | monthly | Mar 12 |
  | Amazon Prime | $14 | monthly | Mar 20 |
  | iCloud+ | $3 | monthly | Mar 18 |
  | Notion | $10 | monthly | Mar 25 |
  | GitHub Pro | $4 | monthly | Mar 22 |
  | Figma | $15 | monthly | Mar 28 |
  | ChatGPT | $20 | monthly | Mar 30 |

#### 4.3 Cancel Subscription Action
- **What happens**: Clicking cancel shows confirmation
- **UI Elements**: Cancel button (`.cancel-btn`)
- **Interactions**:
  - **Click Cancel**:
    1. Shows `confirm()` dialog: "Cancel {name}? This is a demo - no real cancellation."
    2. If confirmed, shows alert: "{name} subscription marked for cancellation."
- **Data/State Changes**: None (demo only)

---

## 5. Dashboard → Travel

### Flow Overview
```
Travel Detail → View Trips
```

### Pathway Details

#### 5.1 Travel Detail View
- **What happens**: Shows upcoming trip details
- **UI Elements**:
  - Back button ("← Back")
  - Title: "Travel"
  - Upcoming Trips list

#### 5.2 Trip Cards
- **What happens**: Each trip displayed as a card with details
- **UI Elements**: `.trip-card` containing:
  - Date badge (month + day)
  - Destination name
  - Airline + Confirmation code
- **Interactions**:
  - **Hover**: Card lifts with border highlight and translateX
  - **Click**: None (display only in current implementation)
- **Trips**:
  | Destination | Dates | Airline | Confirmation |
  |-------------|-------|---------|--------------|
  | Tokyo, Japan | Mar 22-29 | United | TK2947 |
  | New York, NY | Apr 15-18 | Delta | DL1882 |

---

## 6. Dashboard → Calendar

### Flow Overview
```
Calendar Detail → View Month → Click Date → View Events
```

### Pathway Details

#### 6.1 Calendar Detail View
- **What happens**: Shows monthly calendar with events
- **UI Elements**:
  - Back button ("← Back")
  - Title: "Calendar"
  - Month header: "March 2026"
  - Calendar grid (`.calendar-grid`)
  - Upcoming Events list

#### 6.2 Calendar Grid
- **What happens**: Interactive calendar showing days of month
- **UI Elements**:
  - Day headers (Sun, Mon, Tue, Wed, Thu, Fri, Sat)
  - Day cells (`.calendar-day`) for 1-31
- **States**:
  - **Today** (Mar 8): `.today` class, purple gradient background
  - **Has Event**: `.has-event` class, shows pink dot indicator
- **Interactions**:
  - **Hover**: Background changes to hover color
  - **Click**: None (display only in current implementation)
- **Days with Events**:
  | Date | Event |
  |------|-------|
  | 9 | Team Standup |
  | 12 | Lunch with Sarah |
  | 18 | Dentist |
  | 22 | Flight to Tokyo |

#### 6.3 Events List
- **What happens**: Shows all upcoming events
- **UI Elements**: `.event-item` elements containing:
  - Time
  - Event name
  - Source (Google Calendar or Email)
- **Events**:
  | Time | Name | Source |
  |------|------|--------|
  | 9:00 AM | Team Standup | Google Calendar |
  | 12:30 PM | Lunch with Sarah | Email |
  | 3:00 PM | Dentist | Email |
  | 10:00 AM | Flight to Tokyo | Email |

---

## 7. Dashboard → Settings

### Flow Overview
```
Settings Detail → Toggle Preferences → Disconnect Account
```

### Pathway Details

#### 7.1 Settings Detail View
- **What happens**: User configures account and preferences
- **UI Elements**:
  - Back button ("← Back")
  - Title: "Settings"
  - Account section
  - Preferences section

#### 7.2 Account Section
- **UI Elements**:
  - Section title: "Account"
  - Email display: "ryan@example.com"
  - "Disconnect" button (`.disconnect-btn`)
- **Interactions**:
  - **Click Disconnect**:
    1. Shows `confirm()` dialog: "Disconnect your email account?"
    2. If confirmed, returns to landing screen via `showScreen('landing')`
- **Data/State Changes**: Returns to landing, session cleared

#### 7.3 Preferences Section
- **UI Elements**:
  - Section title: "Preferences"
  - 3 settings items with toggles:
    1. **Dark Mode** - "Use dark theme"
    2. **Email Notifications** - "Get alerts for new insights"
    3. **Weekly Summary** - "Receive weekly digest"
- **Toggle Component**:
  - `.toggle` element
  - `.active` class when enabled
  - CSS thumb slides left/right on toggle
- **Interactions**:
  - **Click Toggle**:
    1. Toggles `.active` class
    2. Updates localStorage with setting
    3. Persists across sessions
- **Data/State Changes**:
  - localStorage key: `settings`
  - Stores object: `{ darkMode: boolean, notifications: boolean, weeklySummary: boolean }`

#### 7.4 Settings State Persistence
- **On Load**: `DOMContentLoaded` reads localStorage and applies saved settings
- **On Toggle**: Updates localStorage immediately

---

## 8. Dashboard → Create Custom Dashboard

### Flow Overview
```
Home → Create Dashboard Button → Modal → Select Type → Create → View Custom Dashboard
```

### Pathway Details

#### 8.1 Opening Create Modal
- **What happens**: User clicks "Create Dashboard" button
- **UI Elements**:
  - "+ Create Dashboard" button (`.create-dashboard-btn`)
  - Modal overlay (`.modal-overlay`)
- **Interactions**:
  - **Click Button**: Opens modal with `openCreateModal()`
  - **Click Backdrop**: Closes modal
  - **Press Escape**: Closes modal

#### 8.2 Dashboard Type Selection
- **UI Elements**: 4 dashboard options in grid:
  1. Fitness (💪)
  2. Food & Dining (🍔)
  3. Shopping (🛍️)
  4. Work (💼)
- **Interactions**:
  - **Click Option**: 
    1. Adds `.selected` class to clicked option
    2. Removes from others
    3. Sets `selectedDashboardType` variable
- **State Changes**: `selectedDashboardType` = selected type or null if none selected

#### 8.3 Create Dashboard Action
- **What happens**: Click "Create with AI" button
- **UI Elements**:
  - "✨ Create with AI" button (`.ai-build-btn`)
- **Interactions**:
  - **Click Create**:
    1. Gets existing dashboards from localStorage
    2. If no type selected, randomly selects one
    3. Creates dashboard object with id, type, icon, name
    4. Saves to localStorage
    5. Closes modal
    6. Shows alert: "Dashboard created!"
    7. Re-renders custom dashboards section
- **Data/State Changes**:
  - localStorage key: `customDashboards`
  - Array of objects: `[{ id: timestamp, type: string, icon: emoji, name: string }]`

#### 8.4 Custom Dashboards Display
- **What happens**: Custom dashboards appear on Home screen
- **UI Elements**:
  - Section header: "Your Custom Dashboards"
  - Grid of custom dash cards (`.custom-dash-card`)
  - Each card has:
    - Icon
    - Name
    - Delete (×) button (visible on hover)
- **Interactions**:
  - **Click Card**: Opens custom dashboard modal via `openCustomDashboard(name)`
  - **Click Delete**: Removes from localStorage and re-renders

#### 8.5 Custom Dashboard Modal
- **What happens**: Shows detailed view of custom dashboard
- **UI Elements**:
  - Modal with icon and name header
  - Stats row (4 stats)
  - Recent Activity list (4 items)
  - Close button
- **Mock Data by Type**:
  - **Fitness**: $127/mo, Classes: 12, Streak: 7 days, Goal: 75%
  - **Food & Dining**: $623/mo, Orders: 18, Restaurants: 9, Avg: $35
  - **Shopping**: $412/mo, Orders: 7, Returns: 1, Saved: $45
  - **Work**: $89/mo, Tools: 6, Projects: 4, Team Size: 3
- **Interactions**:
  - **Click Close**: Closes modal

---

## 9. Mobile: Hamburger Menu

### Flow Overview
```
Mobile View → Open Hamburger → Navigate → Close on Selection
```

### Pathway Details

#### 9.1 Mobile View Detection
- **Breakpoint**: Window width < 768px
- **UI Changes**:
  - Hamburger button appears (`.hamburger`)
  - Sidebar hidden by default (transform: translateX(-100%))
  - Dashboard grid: 2 columns
  - Stats row: 2 columns

#### 9.2 Opening Sidebar
- **What happens**: User taps hamburger menu
- **UI Elements**:
  - Hamburger button (☰)
  - Overlay (`.hamburger-overlay`)
  - Sidebar (`.sidebar`)
- **Interactions**:
  - **Click Hamburger**:
    1. Toggles `.open` class on sidebar
    2. Toggles `.active` class on overlay
- **State Changes**: Sidebar slides in from left

#### 9.3 Navigation via Mobile Sidebar
- **What happens**: User selects nav item
- **Interactions**:
  - **Click Nav Item**:
    1. Navigates to section (same as desktop)
    2. Calls `closeSidebarMobile()` which removes .open and .active classes
- **Sidebar Items**: Same as desktop (Home, Spending, Subscriptions, Travel, Calendar, Settings)

#### 9.4 Closing Sidebar (Alternative Methods)
- **Click Overlay**: Closes sidebar
- **Navigate to Section**: Auto-closes
- **Resize to Desktop**: Auto-shows sidebar

---

## Summary: All Interactive Elements

### Buttons/Actions
| Element | Location | Action |
|---------|----------|--------|
| Connect Your Email | Landing | `showScreen('providers')` |
| Gmail/Outlook/Yahoo/iCloud | Providers | `connectProvider()` |
| Back (all detail views) | Detail headers | `showDashboardHome()` |
| Home card clicks | Dashboard | `showDetail()` |
| Sidebar nav items | Sidebar | `showDetail()` / `showDashboardHome()` |
| Category items | Spending | `toggleCategory()` |
| Chart segments toast + expands category |
 | Spending | Shows| Cancel buttons | Subscriptions | `cancelSubscription()` |
| Toggle switches | Settings | `toggleSetting()` |
| Disconnect | Settings | `disconnect()` |
| Create Dashboard | Home | `openCreateModal()` |
| Dashboard type options | Create Modal | `selectDashboard()` |
| Create with AI | Create Modal | `createDashboard()` |
| Custom dashboard cards | Home | `openCustomDashboard()` |
| Delete custom dashboard | Home | `deleteDashboard()` |
| Hamburger | Mobile | `toggleSidebar()` |

### State Storage
| Key | Storage Type | Purpose |
|-----|--------------|---------|
| `customDashboards` | localStorage | Array of user-created dashboards |
| `settings` | localStorage | User preferences (dark mode, notifications, etc.) |

---

*Document generated from: `~/.openclaw/workspace/email-dashboard-prototype/index.html`*
*Last Updated: March 2026*

# MailSight User Pathway Document

## Product: MailSight - AI Email Dashboard

This document outlines the complete user journey for MailSight, from initial discovery through ongoing usage. It serves as a reference for the design team to ensure the prototype reflects a complete, polished user experience.

---

## 1. Full User Pathway Overview

```
[Landing] → [Email Connect] → [Processing] → [Dashboard] → [Ongoing Use]
```

### Pathway Summary

| Stage | User Goal | Key Action | Time to Next Stage |
|-------|-----------|------------|-------------------|
| Landing | Understand value, get started | Click "Connect Email" | Immediate |
| Email Connect | Securely connect inbox | Authorize provider | 30-90 seconds |
| Processing | See AI analyze emails | Wait for completion | 1-3 minutes |
| Dashboard | View insights & take action | Explore dashboards | Ongoing |
| Ongoing | Stay informed, take action | Return to app | Weekly/monthly |

---

## 2. Detailed Stage Breakdown

### Stage 1: Landing

**What the User Sees**
- Clean, modern landing page with value proposition
- Hero section with tagline: "Transform Your Inbox into Insights"
- Four dashboard preview cards showing: Spending, Subscriptions, Travel, Calendar
- Clear primary CTA: "Connect Your Email" button
- Trust indicators: "Secure," "Private," "Free to start"
- Subtle animated background or data visualization

**What the User Does**
1. Lands on page (from ad, search, referral)
2. Scrolls to understand features
3. Views dashboard previews
4. Clicks "Connect Your Email" button

**What the User Feels**
- Curious about what the product does
- Hopeful that email chaos can be organized
- Slight skepticism about security (normal)
- Eagerness to see their data visualized

**Key Decisions Made**
- First impression: Is this worth my time? → YES
- Trust assessment: Can I trust this with my email? → YES/NO
- Action decision: Do I proceed to connect? → YES

**Success Metrics**
- Landing page conversion rate: Target 40%+
- Bounce rate: Target <50%
- Time on page: Target 30+ seconds
- CTA click-through: Target 25%+

---

### Stage 2: Email Connect

**What the User Sees**
- Provider selection screen with logos: Gmail, Outlook, Yahoo, iCloud, Other IMAP
- Clean grid or list layout
- Each provider shows icon + name
- Subtext: "We only read your emails - we never send anything"
- "Back" option if reconsidering

**What the User Does**
1. Selects email provider
2. Redirected to provider's OAuth login (or IMAP credentials)
3. Enters email and password
4. Reviews permissions requested
5. Grants access
6. Redirected back to app

**What the User Feels**
- Minor friction from login process
- Some privacy concern (normal, expected)
- Relief when familiar OAuth flow appears
- Anxiety during permission review → resolved when seeing "read only"
- Satisfaction when connected successfully

**Key Decisions Made**
- Provider selection: Which email to use?
- Permission grant: Is this level of access acceptable? → YES
- Trust confirmation: "This feels safe"

**Success Metrics**
- Provider selection completion: Target 80%+
- OAuth success rate: Target 90%+
- Permission approval rate: Target 85%+
- Drop-off at provider screen: Target <20%

---

### Stage 3: Processing

**What the User Sees**
- Animated processing screen
- Visual: Email inbox being scanned, AI icon "reading" emails
- Progress indicator: "Analyzing your emails..." / "Found 3 subscriptions" / "Detecting travel bookings..."
- List of discovered items updating in real-time
- Estimated time remaining (if > 30 seconds)
- Optional: Sample insights appearing as they're found

**What the User Does**
1. Watches the processing animation
2. Sees discoveries appear (subscriptions, purchases, trips)
3. Optionally reads what was found
4. Waits for completion

**What the User Feels**
- Anticipation - "What's it finding?"
- Engagement - fun to watch discoveries appear
- Reassurance - seeing data extracted builds confidence
- Impatience if taking too long (>2 min)
- Excitement as items populate

**Key Decisions Made**
- Continue waiting vs. leave → STAY
- Trust the process → YES

**Success Metrics**
- Processing completion rate: Target 85%+
- Average processing time: Target <90 seconds
- User abandonment during processing: Target <15%
- User satisfaction during wait: Target 4/5+

---

### Stage 4: Dashboard

**What the User Sees**
- **Dashboard Home** with overview cards:
  - Spending summary card (this month's total)
  - Subscriptions card (active count, monthly cost)
  - Travel card (upcoming trips)
  - Calendar card (events this week)
- Navigation to detailed views
- Welcome message with quick insights
- Settings icon (top right)

**What the User Does**
1. Lands on dashboard overview
2. Clicks into each dashboard to explore
3. Views detailed data, charts, lists
4. Takes actions (cancel subscription, view boarding pass)
5. Adjusts settings if needed

**What the User Feels**
- Delight - "Wow, it found all this!"
- Satisfaction - organized view of email chaos
- Empowerment - actionable insights
- Engagement - want to explore more
- Minor overwhelm if too much data (manageable)

**Key Decisions Made**
- Which dashboard to explore first?
- Which insights to act on?
- Settings adjustments needed?
- Share with others? (referral)

**Success Metrics**
- Dashboard visit rate: Target 90%+
- Feature discovery (4 dashboards viewed): Target 60%+
- Time on first session: Target 5+ minutes
- Return visit intent: Target 70%+
- User satisfaction: Target 4.5/5+

---

### Stage 5: Ongoing Use

**What the User Sees**
- Returning visit → Dashboard shows updated data
- New items highlighted since last visit
- Notifications/badges for new discoveries
- Weekly summary email (optional)
- Settings for preferences

**What the User Does**
1. Returns to app (direct, email, notification)
2. Checks updated insights
3. Takes action on new items
4. Explores deeper into dashboards
5. Manages settings and preferences

**What the User Feels**
- Habit formation - "I check this weekly"
- Trust - data is accurate and helpful
- Value recognition - "This is worth it"
- Ownership - personalized to their usage

**Key Decisions Made**
- Frequency of return: Daily? Weekly? Monthly?
- Which features to prioritize?
- Upgrade to premium? (if applicable)
- Refer friends?

**Success Metrics**
- Day 1 retention: Target 40%+
- Day 7 retention: Target 20%+
- Day 30 retention: Target 10%+
- Weekly active users: Target 25% of users
- Monthly active users: Target 40% of users
- NPS Score: Target 50+

---

## 3. User Personas

### Persona 1: Sarah - The Busy Professional

**Demographics**
- Age: 32
- Role: Marketing Manager
- Income: $85,000/year
- Tech comfort: High

**Goals**
- Understand where money goes without tracking manually
- Never miss a subscription charge
- Keep travel plans organized in one place

**Pain Points**
- Manually checking bank statements
- Forgetting subscription renewal dates
- Losing travel confirmation emails
- Email inbox is chaotic

**Behaviors**
- Checks email 20+ times/day on phone
- Has 500+ unread emails
- Uses Gmail for personal and work
- Shops online frequently
- Has 8+ active subscriptions

**User Pathway Experience**

| Stage | Sarah's Experience |
|-------|-------------------|
| Landing | Sees "Spending" card first - that's her priority. Clicks connect immediately. |
| Connect | Uses Google OAuth - familiar, fast. Grants read access without hesitation. |
| Processing | Watches eagerly as subscriptions appear. "Oh wow, it found my Netflix and Spotify!" |
| Dashboard | Spends 10 minutes in Spending Dashboard. Loves the monthly breakdown chart. |
| Ongoing | Returns every Monday to check the previous week's spending. |

**Success Triggers**
- First-time insight: "I spent $340 on subscriptions?!"
- Action taken: Canceled unused gym membership
- Emotional: Relieved to have clarity

---

### Persona 2: Marcus - The Family Planner

**Demographics**
- Age: 41
- Role: Operations Director
- Income: $120,000/year
- Tech comfort: Medium

**Goals**
- Keep family travel organized
- Track family expenses
- Never miss important event RSVPs

**Pain Points**
- Losing hotel booking confirmations
- Forgetting to RSVP to events
- Not knowing upcoming bills
- Family expenses scattered across cards

**Behaviors**
- Uses Outlook for work, Gmail for personal
- Travels 4-6 times/year for family vacations
- Shares subscriptions with family members
- Checks email 5-10 times/day

**User Pathway Experience**

| Stage | Marcus's Experience |
|-------|-------------------|
| Landing | Drawn to "Travel Dashboard" preview. Family trips are stressful to organize. |
| Connect | Uses personal Gmail. Slightly nervous about permissions - reads carefully. |
| Processing | Excited to see upcoming trip appear. "It's finding my Hawaii booking!" |
| Dashboard | Immediately clicks Travel Dashboard. Scrolls through itinerary details. |
| Ongoing | Checks Travel Dashboard before each trip. Uses Calendar for kid's events. |

**Success Triggers**
- First-time insight: Boarding pass auto-saved to Apple Wallet
- Action taken: Downloaded itinerary PDF for offline access
- Emotional: One less thing to worry about

---

## 4. Edge Cases

### Edge Case 1: Email Connect Fails

**Scenario:** User's OAuth fails or credentials are incorrect

**What User Sees**
- Error message: "Unable to connect. Please try again."
- Specific error: "Invalid credentials" or "Permission denied"
- "Try Again" button
- "Need help?" link

**User Feelings**
- Frustration - "This isn't working"
- Abandonment risk - might leave
- Confusion - unclear what went wrong

**Resolution Path**
1. User clicks "Try Again"
2. Redirected back to provider selection or OAuth
3. If persistent failure → Help article or support contact
4. Alternative: Offer IMAP manual setup as backup

**Design Requirements**
- Clear, friendly error messages
- Retry option prominently displayed
- Help link for troubleshooting
- Log error details for support

---

### Edge Case 2: No Data Found

**Scenario:** Email account has no parseable data (new account, no purchases, etc.)

**What User Sees**
- Processing completes quickly (<10 seconds)
- Dashboard shows: "We didn't find much yet!"
- Empty states for each dashboard
- Encouraging message: "Connect more accounts or keep using email - we'll find more!"

**User Feelings**
- Confusion - "Is it working?"
- Disappointment - expected insights
- Concern - wasted time

**Resolution Path**
1. Explain that data builds over time
2. Suggest connecting additional email accounts
3. Show what types of emails to look for
4. Offer to send test data or demo account

**Design Requirements**
- Friendly empty states with illustrations
- Educational content on what data is detected
- Clear call-to-action to keep using email
- Optional: Demo/preview account to see possibilities

---

### Edge Case 3: Partial Data / Limited Permissions

**Scenario:** User grants only email read, not full access

**What User Sees**
- Dashboard shows available insights only
- Some dashboards may be empty or limited
- Banner/notice: "Enable full access for more insights"

**User Feelings**
- Confusion about what's missing
- Decision: Upgrade permissions or stay as-is

**Resolution Path**
1. Show value of what's available
2. Clearly explain what additional access enables
3. Make re-authorization easy
4. Don't block - work with what they gave

**Design Requirements**
- Transparent about what's missing
- Non-intrusive upgrade prompts
- Clear value proposition for full access

---

### Edge Case 4: Large Email Account (Slow Processing)

**Scenario:** User has 50,000+ emails, processing takes >3 minutes

**What User Sees**
- Longer processing time estimate: "This may take a few minutes..."
- Progress continues updating
- Option to process in background and email results

**User Feelings**
- Impatience
- Concern about performance

**Resolution Path**
1. Show detailed progress ("Found 1,000 purchases...")
2. Offer background processing option
3. Prioritize recent emails for faster initial results
4. Send email when complete

**Design Requirements**
- Accurate time estimates
- Engaging progress updates
- Background option for large accounts
- Email/SMS notification when done

---

### Edge Case 5: Security / Privacy Concern Mid-Flow

**Scenario:** User stops during permissions screen, concerned about data

**What User Sees**
- Provider's OAuth permission screen
- "Read your email" permission listed
- Option to cancel/deny

**User Feelings**
- Anxiety about privacy
- Need for reassurance

**Resolution Path**
1. Trust signals throughout the flow
2. Clear "We never send email" message
3. Privacy policy easily accessible
4. Option to disconnect anytime

**Design Requirements**
- Trust badges on every screen
- Clear privacy statement
- Easy disconnect option in settings
- No hidden permissions

---

### Edge Case 6: Session Timeout

**Scenario:** User leaves during processing, returns later

**What User Sees**
- If processing complete → Dashboard
- If still processing → Resume screen with progress
- If failed → Option to restart

**User Feelings**
- Confusion about state
- Concern about data loss

**Resolution Path**
1. Persist state in database
2. Resume seamlessly on return
3. Clear status indicators
4. Never lose discovered data

**Design Requirements**
- Save progress state
- Resume processing on return
- Clear status messages
- No duplicate processing

---

## 5. Success Metrics Summary

### Acquisition Stage (Landing → Connect)

| Metric | Target | Measurement |
|--------|--------|-------------|
| Landing page visits | 10,000/month | Analytics |
| CTA click-through rate | 25%+ | Click/Visit |
| Bounce rate | <50% | Single page exits |
| Time on page | 30+ seconds | Avg session |
| Email connect started | 40%+ | OAuth start |

### Connection Stage (OAuth Flow)

| Metric | Target | Measurement |
|--------|--------|-------------|
| OAuth success rate | 90%+ | Auth completions |
| Provider selection → Auth | 80%+ | Funnel analysis |
| Permission approval | 85%+ | Grant rate |
| Average connect time | <60 sec | Auth duration |

### Processing Stage

| Metric | Target | Measurement |
|--------|--------|-------------|
| Processing completion | 85%+ | Full completion |
| Avg processing time | <90 sec | Duration |
| User wait tolerance | >2 min | Drop-off curve |
| Satisfaction during wait | 4/5+ | In-app survey |

### Dashboard Stage (First Session)

| Metric | Target | Measurement |
|--------|--------|-------------|
| Dashboard visit | 90%+ | Any dashboard view |
| All dashboards viewed | 60%+ | 4+ dashboards |
| Time on app (first session) | 5+ min | Session duration |
| Return intent | 70%+ | "Would you return?" |
| First-session satisfaction | 4.5/5+ | Exit survey |

### Ongoing Usage (Retention)

| Metric | Target | Measurement |
|--------|--------|-------------|
| Day 1 retention | 40%+ | Day 1 return |
| Day 7 retention | 20%+ | Week 1 return |
| Day 30 retention | 10%+ | Month 1 return |
| Weekly active rate | 25%+ | Weekly usage |
| Monthly active rate | 40%+ | Monthly usage |
| NPS Score | 50+ | Quarterly survey |

### Action Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| Subscription cancelled | 5%+ | Action tracked |
| Budget alerts set | 15%+ | Settings changed |
| Calendar synced | 20%+ | Integration used |
| Referral made | 10%+ | Share actions |

---

## 6. Design Recommendations

Based on this pathway analysis:

1. **Trust is paramount** - Every screen needs trust indicators, especially around email access
2. **Processing must delight** - This is the "wow moment" - make it engaging
3. **Empty states matter** - Not everyone has data; handle gracefully
4. **Onboarding is continuous** - Discovery happens over days, not one session
5. **Mobile is critical** - Most users will check on phone
6. **Notifications drive retention** - Push new findings to bring users back

---

*Document Version: 1.0*  
*Created for: MailSight Design Team*  
*Purpose: User experience reference for prototype development*

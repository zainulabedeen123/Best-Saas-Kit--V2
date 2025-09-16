# Product Requirements Document: The "Viral Business Plan Generator"

## 1. Objective & Vision

*   **Objective:** To create the simplest, most engaging AI-powered tool that allows aspiring entrepreneurs to generate a preliminary business plan in minutes.
*   **Vision:** To become the go-to starting point for every new business idea, fostering a community of founders who build and share their visions openly. The app's success is tied to its users' success in articulating and sharing their ideas.

## 2. Target Audience

*   **Primary:** Aspiring entrepreneurs, students in business classes, hackathon participants.
*   **Secondary:** Small business owners seeking to formalize their strategy, freelancers creating a business case for their services.

## 3. Core User Experience & "The Viral Loop"

The core of the app will be a guided, conversational AI that walks the user through creating their business plan. The "viral" component is a beautifully designed, one-page summary that users will be proud and excited to share.

**User Flow:**

1.  **Instant Onboarding:** User lands on the page and can start interacting with the AI immediately. Sign-up (via Google) is only required to save progress or export.
2.  **Conversational Builder:** The AI asks one question at a time in a chat interface (e.g., "What is the name of your business?", "In one sentence, what problem are you solving?").
3.  **Real-time Draft:** As the user answers, a business plan document is built in real-time on the side of the screen, giving an immediate sense of progress.
4.  **The "Magic" Moment (The Viral Asset):** Once the core sections are complete, the user clicks "Generate My One-Pager". The AI synthesizes the information into a visually stunning, infographic-style, one-page business plan. This is the key shareable asset.
5.  **The Share & Grow Loop:**
    *   The user is presented with easy, one-click options to share their one-pager on LinkedIn, Twitter, and other social platforms with a pre-populated message like: "I just created a business plan for my new idea, [Business Name]! Check it out and let me know what you think. Built with [Your App's Name]."
    *   This shared image/link drives new users to the app, restarting the loop.

## 4. Feature Breakdown

#### **Must-Have Features (MVP):**

*   **AI-Powered Conversational Guide:**
    *   Guides users through essential business plan sections:
        *   Problem Statement
        *   Solution / Value Proposition
        *   Target Market
        *   Marketing & Sales Strategy
        *   Team
        *   Mission Statement
*   **Real-Time Document Preview:** A live-updating preview of the business plan.
*   **One-Page Summary Generator:**
    *   Creates a visually appealing, infographic-style summary.
    *   Must be branded with a subtle watermark/logo of the app to drive attribution.
    *   Multiple modern templates to choose from.
*   **Social Sharing Integration:** One-click sharing of the one-page summary.
*   **Freemium Model:**
    *   **Free Tier:** Allows creation of one full business plan and the one-page summary. This is crucial for virality.
    *   **Pro Tier (Subscription):** Unlocks advanced features.

#### **Advanced Features (Pro Tier):**

*   **AI Financial Projections:** The AI asks for key assumptions (e.g., price, number of customers) and generates a 3-year financial forecast (P&L, Cash Flow).
*   **Expanded Business Plan Sections:** Adds sections like Competitive Analysis, SWOT Analysis, and Detailed Milestones.
*   **Premium Export Templates:** More one-pager designs and professional templates for the full business plan (PDF, DOCX).
*   **Team Collaboration:** Allow users to invite co-founders to view, comment on, and edit the plan in real-time.
*   **"Pitch My Idea" Mode:** The AI generates a 60-second elevator pitch script and a 10-slide pitch deck outline based on the plan.

## 5. Monetization (Leveraging the Template's Stripe Integration)

*   **Free Plan:** The core viral loop. 1 plan per user.
*   **Pro Subscription ($10/month):** Unlimited plans and access to all advanced features. This is for serial entrepreneurs, consultants, and power users.
*   **Credit System (Pay-as-you-go):** Free users can purchase credits to unlock a single Pro feature for one plan (e.g., "Unlock Financial Projections for this plan for 50 credits"). This creates a low-friction path to conversion.

## 6. Success Metrics

*   **Viral Coefficient (k-factor):** The number of new users brought in by each existing user. (Tracked via UTM links on shared summaries).
*   **Activation Rate:** % of new users who complete at least 50% of a business plan.
*   **Conversion Rate:** % of free users who upgrade to Pro or purchase credits.
*   **Sharing Rate:** % of completed plans that result in a social media share.

## 7. Technical Implementation Notes

*   The existing SaaS template is a perfect foundation.
*   **Frontend:** Use Next.js. Focus on a slick, responsive UI with smooth animations (Framer Motion) to make the experience feel premium.
*   **Backend:** The existing API structure can be used. The core logic will be in the `/api/chat` endpoint.
*   **AI:** Use a powerful model from OpenRouter (like GPT-4o or Claude 3 Opus) for the conversational AI to ensure high-quality, human-like interaction and summarization.
*   **Database:** The Neon PostgreSQL database will store user plans, section by section, allowing for easy updates and real-time saving.

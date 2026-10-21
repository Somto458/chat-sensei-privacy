# Privacy Policy — Chat Sensei

**Effective date:** October 21, 2026  
**App name:** Chat Sensei  
**Android application ID:** `com.chatsensei.app`

This Privacy Policy describes how **NDI apps** (“**we**,” “**us**,” or “**our**”) processes information when you use the Chat Sensei mobile application (the “**App**”). It is based on the App and backend code as implemented in this project.

---

## 1. Summary

Chat Sensei helps you draft replies, coaching feedback, conversation openers, and similar text. Depending on configuration:

- The App may use **Supabase** (authentication, Edge Functions, and database) when you generate content with a live backend connection.
- **AI outputs** are produced on the server by a **built-in mock generator by default**. An **Anthropic (Claude) integration is not implemented** in the current codebase, even if a server secret is configured.
- **Optional photos** you pick in some flows are held **in memory on your device** for your reference; they are **not** included in generation API requests in the current implementation.
- **Google Play subscriptions** (Android) are handled through **Google Play Billing** via the `expo-iap` library. **RevenueCat is not integrated** in the current codebase.
- Much **onboarding and preference data** stays in **local device storage** only.

---

## 2. Information we process

### 2.1 Account and identifiers (Supabase)

When Supabase is configured in the App:

- The App uses **anonymous sign-in** (`signInAnonymously`) to obtain a Supabase user account and session. You are **not** required to provide an email or password for this in the current App.
- Supabase assigns a **user identifier (UUID)** tied to your anonymous account.
- Session tokens are stored using the Supabase client’s auth storage (on mobile, **AsyncStorage** via `@react-native-async-storage/async-storage`).

**Purpose:** Authenticate calls to the `generate-response` Edge Function and associate credit usage with your account.

**Shared with:** Supabase (Auth and Postgres), as our infrastructure provider.

### 2.2 Text you enter for AI features

When you use Reply, Coach, Awkward Situations, or Pickup Lines and the backend is available, the App sends a **HTTPS request** to our Supabase Edge Function `generate-response`. The request includes, as applicable:

| Data | Features | Notes |
|------|----------|--------|
| Incoming message text | Reply | Required for generation |
| Optional context note | Reply, Pickup Lines | Optional |
| Your draft reply | Coach | Required |
| Coach skill identifier | Coach | e.g. confidence, awkward |
| Situation message | Awkward Situations | Required |
| Pickup mode, topic, optional context | Pickup Lines | Photo is **not** sent |
| Tone, locale, batch index | All (where applicable) | Controls style / variation |
| Client-generated idempotency key | All backend generations | Prevents duplicate charges on safe retries |
| Feature name | All | e.g. `reply`, `coach` |

The App **does not** send a user id in the JSON body; the server derives identity from your **Authorization** session token.

**Purpose:** Generate suggestions or coaching feedback and enforce credit rules.

**Processing location:** Supabase Edge Functions (and in-memory processing for mock generation). **We do not store the full text of your prompts in the database tables defined in this project’s migrations** (`ai_generation_requests` stores feature, idempotency key, credits used, and timestamps; `ai_usage` stores feature and credits used). Prompt content may exist transiently in server memory while a request is handled and may appear in **provider logs** only to the extent described in Section 5.

If Supabase is **not** configured, generation may run **entirely on your device** using local mock logic, and that text **does not** leave your device via our backend.

### 2.3 Photos and screenshots

| Flow | Behavior in current App |
|------|-------------------------|
| **Awkward Situations** / **Start Conversation (photo workflow)** | You may pick an image from your library (`expo-image-picker`). The image URI and dimensions are kept in **component state on your device**. Generation requests send **tone and optional text context only**, not the image file or URI. |
| **Reply — “Add screenshot”** | The control shows a placeholder alert only; **no image picker or upload** is implemented on that screen. |

**Purpose (photos):** Your own visual reference while using the App.

**Device permissions:** On native platforms, the App may request **photo library** access to let you choose an image. You can deny permission and still use features that do not require a photo.

### 2.4 Credits and usage records (Supabase database)

When a backend generation succeeds, our server:

- Deducts **credits** from your row in **`public.profiles`** (balance stored server-side).
- Inserts a row into **`public.ai_generation_requests`** (user id, idempotency key, feature, credits used, timestamp).
- Inserts a row into **`public.ai_usage`** (user id, feature, credits used).

**Purpose:** Metering, fraud prevention (idempotency), and operational accounting.

The App may receive **`creditsRemaining`** in the Edge Function response; syncing that value everywhere in the UI is not guaranteed by the current client code.

### 2.5 Subscriptions and premium access (Google Play — Android)

On **Android**, the App uses **Google Play Billing** through **`expo-iap`** for subscription products including:

- `chatsensei_plus_weekly`
- `chatsensei_plus_yearly`

**Google** processes payment and subscription status. The App performs **on-device** checks (purchase state, active subscriptions, product IDs) to set a **local premium flag** in AsyncStorage.

**Not implemented in the current codebase:**

- **Server-side** Google Play purchase verification (see `lib/subscriptions/serverVerificationArchitecture.ts`).
- **RevenueCat** or any other third-party subscription SDK (no dependency or integration in this repository).

**Purpose:** Provide premium access after a valid subscription (and support restore purchases where available).

**Shared with:** Google (Google Play), as the payment and subscription platform.

On platforms where billing is marked unsupported (e.g. iOS in the current billing provider), subscription purchase flows may not be available.

### 2.6 Data stored only on your device

The App uses **AsyncStorage** for items including:

- Supabase auth session (via Supabase client configuration)
- Onboarding completion and style preferences (goals, tones)
- Selected **language**
- **Sensei** on/off preference
- **Premium active** flag (derived from store entitlements)
- **Introductory trial used** flag (local bookkeeping)
- Timestamp of last in-app review prompt

**Purpose:** App functionality, preferences, and gating premium features.

This data is **not** described as synced to our backend in the current code, except where Supabase Auth session data is managed by the Supabase client.

### 2.7 Data we do not collect in the current App

Based on the codebase reviewed for this policy:

- No **RevenueCat** integration.
- No **Claude / Anthropic** API calls in production logic (adapter throws `claude_not_implemented`).
- No analytics SDK (e.g. Firebase Analytics) in dependencies reviewed for this policy.
- No implemented **account deletion** or **export** flow in the App UI.
- No upload of **photo files** to Supabase Storage in the generation paths reviewed.

---

## 3. How we use information

We use the categories above to:

- Provide and improve core features (text generation and coaching).
- Authenticate you to our backend and prevent abuse.
- Manage **credit balances** and **usage records**.
- Process **subscriptions** through Google Play where enabled.
- Remember **preferences** and **onboarding** choices on your device.
- Comply with law and protect the security of our services.

We do **not** sell your personal information. We do **not** use your information for third-party advertising based on the current App implementation.

---

## 4. Legal bases (EEA/UK users)

Where applicable, we rely on:

- **Performance of a contract** — providing the App and features you request.
- **Legitimate interests** — securing the service, preventing fraud, and understanding aggregate usage (e.g. feature-level usage records without storing full prompts in our schema).
- **Consent** — where required for optional permissions (e.g. photo library) or future features we describe separately.

You may withdraw consent for optional permissions in device settings; core text features may still work without photos.

---

## 5. Sharing and service providers

We share information with **service providers** that help us operate the App:

| Provider | Role | Typical data involved |
|----------|------|------------------------|
| **Supabase** | Auth, database, Edge Functions | User id, session tokens, credit/usage records, generation request metadata; **prompt text** in Edge Function requests (transient processing) |
| **Google Play** | Subscriptions and payments (Android) | Purchase and subscription status handled under Google’s policies |
| **Anthropic (Claude)** | **Not used** in the current implementation | N/A today; see Section 7 |

We may also disclose information if required by law or to protect rights, safety, and security.

**Planned (not current):** Backend verification of Google Play purchases using a **Google Play Developer API service account** on a server (documented as recommended, not built). Optional hosted verifiers (e.g. IAPKit via `verifyPurchaseWithProvider`) are mentioned in code comments only. **RevenueCat is not part of the current App.**

Supabase and Google may process data in countries other than your own. Their privacy policies govern their handling.

---

## 6. AI processing

**Current behavior:**

- The Edge Function **`generate-response`** validates your request, generates a response using an **internal mock provider** by default, then deducts credits on success.
- If `ANTHROPIC_API_KEY` is set on the server, the code path still **does not call Claude**; it falls back to mock when the adapter is invoked.

**Future behavior (if we enable it):** We may send the **same categories of prompt text** described in Section 2.2 to an external AI provider (e.g. Anthropic) to produce responses. We will update this policy before enabling that processing.

Edge Function logging in the current code records **events** (e.g. feature name, truncated user id prefix, error reasons) and is **not** designed to log full message content in the snippets reviewed for this policy. Provider and platform logs may still exist separately.

When the backend returns mock output, the response may include a **mock disclaimer** indicating no external AI provider was called.

---

## 7. Subscriptions — implemented vs planned

| Capability | Status in current codebase |
|------------|----------------------------|
| Google Play subscription products (`chatsensei_plus_weekly`, `chatsensei_plus_yearly`) | **Implemented** (Android, via `expo-iap`) |
| Free trial messaging (e.g. 2-day trial copy) | **Implemented** in product UX; eligibility is determined by **Google Play** |
| Restore purchases | **Implemented** (Android) |
| Server-side receipt/token verification | **Not implemented** |
| RevenueCat | **Not integrated** |
| Linking subscription status to Supabase user records | **Not implemented** in reviewed code |

Subscription management (cancel, renew, payment method) is done through **Google Play**, not inside the App’s backend in the current version.

---

## 8. Retention

We retain information for as long as needed to provide the App and meet legal obligations. In general:

- **Server credit and usage rows** persist until deleted as part of account or database administration. Rows in `ai_generation_requests` reference `auth.users` with **ON DELETE CASCADE** in project migrations.
- **Anonymous Supabase accounts** persist until deleted through Supabase Auth/admin processes. The App does **not** currently offer a self-service “delete account” button.
- **Device-stored data** persists until you clear app data, uninstall the App, or the App removes specific keys (e.g. onboarding reset helpers in code).
- **Google Play** retains transaction and subscription records under Google’s policies.

We have **not** defined automated prompt-text retention on the server because full prompts are **not** stored in the migrated schema reviewed for this policy.

Specific retention periods for backend data: **\[CONFIRM RETENTION SCHEDULE OR STATE “UNTIL ACCOUNT DELETION OR AS NEEDED FOR OPERATIONS”\]**.


---

## 9. Security

We use measures appropriate to the service, including:

- **HTTPS** for client-to-Supabase communication.
- **User JWT authentication** for Edge Functions (`verify_jwt = true` for `generate-response`).
- **Publishable Supabase client keys** in the App only (not service-role keys in client code).
- **Row Level Security** and revoked direct table access for sensitive tables such as `ai_generation_requests`, with credit changes via a **SECURITY DEFINER** RPC bound to `auth.uid()`.
- **Idempotency keys** to reduce duplicate billing on retries.

No method of transmission or storage is 100% secure.

---

## 10. Your choices and rights

Depending on your location, you may have rights to access, correct, delete, or restrict processing of personal information, and to object or withdraw consent where processing is consent-based.

**In the App today:**

- Deny or revoke **photo library** permission in device settings.
- **Clear local data** by clearing storage or uninstalling.
- Manage **subscriptions** in Google Play → Payments & subscriptions.

**Account and server data:**

- The App does **not** implement in-app deletion of Supabase anonymous accounts or server-side profile/usage history.

---

## 11. Children’s privacy

Chat Sensei is **not directed at children under 13** (or the minimum age in your jurisdiction), and we do not knowingly collect personal information from children.

**\[CONFIRM MINIMUM AGE / STORE LISTING AGE RATING ALIGNMENT\]**

---

## 12. Changes to this policy

We may update this Privacy Policy. We will post the revised policy with a new **Effective date** and, where required, provide additional notice in the App or on **\[PRIVACY POLICY URL\]**.

---

*This document was prepared from the Chat Sensei application and Supabase backend source in this repository. It is not legal advice.*

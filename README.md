My Family Reminder App
======================

**Purpose:**
A simple, easy-to-use app that helps users remember important family events (birthdays, anniversaries, baptisms, death days, etc.) by sending timely notifications. Designed especially for users who may struggle with technology, such as elders.

**Core Features:**
- **Onboarding:**
  - Guided onboarding flow to help users enter their family data.
  - Users add family members, specifying name, sex, and date of birth (DOB). All other dates (anniversary, baptism, etc.) are added as events, not as direct fields.
  - Relationships are flexible and link-based, not limited to a single type per member.
  - Clarifying questions to help build a family tree (e.g., "Is this your child, sibling, grandchild?").
  - All data is stored locally on the device for privacy.

- **Adding Reminders:**
  - Simple "+" button to add a new reminder.
  - Easy form to select event type (birthday, anniversary, baptism, etc.) from a list of common events.
  - For birthdays, ask for name, relationship, and date of birth.
  - For anniversaries, ask for names, relationship, and date.
  - Checkbox to enable/disable reminders for each event.

- **Reminder Settings:**
  - Global and per-event reminder options (e.g., 14 days, 7 days, 3 days before the event).
  - **Customizable reminder time:** Users can set a default reminder time (e.g., 9am) in settings, and override per event (e.g., 10am for a birthday, 7pm for an anniversary).
  - Reminders include helpful context (e.g., "John turns 8 in 14 days", "Mary & Tom's 25th anniversary in 7 days").
  - Reminders are actionable, giving enough time to send cards, gifts, or flowers.

- **Backup & Restore:**
  - Users can export a complete backup of all app data (family members, events, notes, relationships, and all images) to a ZIP file containing a JSON manifest and all images. Restore/import reads the backup ZIP, restores the database and images, and updates all image paths. All data remains local and private.
  - Uses kotlinx.serialization with @Contextual for robust serialization of all data, including LocalDate fields.

- **Family Tree Visualization:**
  - Visual family tree interface that populates as users add family members and define relationships. The tree supports complex, non-traditional, and extended relationships (e.g., multiple parents, friends, custom types).
  - Tap on a family member to view or edit their details and reminders.
  - Supports extended and custom relationships (second cousins, friends, friend's children, etc.) and custom event types (graduations, AA milestones, remembrance, etc.).
  - **PET_OF relationship:** Pets can be added and are shown as small icons near their associated person in the tree.

- **Branding & Theming:**
  - App color palette matches the tree logo: deep brown, red, orange, yellow, green, white, blue (for boys), and pink (for girls).
  - Palette applied across all screens and components for a cohesive look.
  - All major dialogs/screens use a consistent BrandedDialog composable for full-screen modals, with a unique screen ID for debugging.

- **Accessibility & UX:**
  - Large, readable text and clear buttons for ease of use by elders.
  - Simple, uncluttered navigation and flows.
  - Accessibility features (content descriptions, haptic feedback, etc.) following best practices.
  - All date pickers use the Material3 modal pattern with a calendar icon; no manual date entry.
  - Quality-of-life improvements: larger floating action button, confirmation dialog on back/exit, improved dropdown/date/time pickers.

- **Privacy:**
  - All data remains on the device; no cloud storage or external sync.

**Motivation:**
Inspired by real needs—helping users (like the app creator's wife) remember the ages, birthdays, and anniversaries of a large family, including grandkids and siblings.

**Design Goals:**
- Prioritize simplicity and clarity in every flow.
- Make it easy to add, view, and edit family reminders.
- Ensure the app is usable and friendly for all ages, especially elders.
- Provide timely, actionable reminders with clear information.
- Visualize family relationships in an intuitive family tree.

**Developer/Test Features:**
- On first install, if a `test.json` file is present in `res/raw/`, the app will auto-populate the database with a comprehensive family and event data set for testing/demo purposes. This logic is modular and will be removed for production builds.
- All data remains local and private, including test data.

**Relationship Management:**
  - Add, view, and remove multiple relationships for each member (e.g., parent, child, friend, etc.) from the profile screen.
  - All relationship data is stored as links between members, supporting complex family structures.

**Technical Debt:**
- Some deprecated Compose APIs are still in use (e.g., menuAnchor, Divider, icons). Planned migration to newer APIs in a future update.
- Ongoing: Compose API cleanup, dialog polish, and accessibility improvements.

## TODO
- Upgrade notes system to support rich text/Markdown editing and display (profile and event notes) when Compose RichText or a similar library supports Kotlin 2.x and Compose 2024+.

TODO: Onboarding should create a 'self' user for better initial data population and guidance.

TODO: Clarify delete actions on the people screen; users are unclear if delete is for the person or the event. Consider best practices for clearer UI/UX (e.g., tooltips, confirmation dialogs, icon labels, or grouping actions).


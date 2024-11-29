Here's a prompt guide for developing a secure, user-friendly, and feature-rich blood pressure app using React PWA with PocketBase as the backend:

## Project Setup

1. Initialize a new Vite project with React and TypeScript
2. Install and configure Tailwind CSS
3. Set up VitePWA plugin for PWA functionality
4. Configure vite-plugin-mkcert for HTTPS during development
5. Set up PocketBase as the backend

## Authentication

1. Implement OAuth2 authentication with GitHub provider using PocketBase
2. Create a secure login page with error handling
3. Implement an error boundary for the entire app
4. Add multi-language support using react-i18next with de.json and en.json files

## App Structure

1. Create a responsive layout with a sidebar and header
2. Implement dark and light themes based on the provided images
3. Add a profile avatar in the header with links to the profile and logout

## Pages and Components

1. Login Page
   - Add OAuth2 login button for GitHub
   - Include PWA installation button

2. Dashboard
   - Create a quick entry form for blood pressure readings
   - Display the last 3 measurements (configurable in user settings)
   - Show a report for the last month

3. Measure Page
   - Implement a generic CRUD component with card and table views
   - Add sorting and filtering functionality
   - Display "created" and "updated" fields as read-only

4. Reports Page
   - Implement filters for data selection
   - Create various charts to visualize blood pressure data

5. User Profile Page
   - Display user avatar and name
   - Allow users to update settings (theme, default page size, language)
   - Store user settings in PocketBase users collection

6. FAQ Page
   - Create a simple FAQ section with common questions and answers

## Data Management

1. Implement efficient data fetching and caching strategies
2. Use PocketBase best practices for pagination
3. Encrypt sensitive user data before storing in PocketBase

## Offline Functionality

1. Implement offline data storage and synchronization
2. Add a visual indicator for offline mode
# Prompt

Generate only the prompt guide without code for a secure, error handling with error boundary, performance, user-friendly, secure (encrypted private data) mobile first, full responsive for mobile and larger screens, gdpr compliance,  caching, react pwa with pocketbase as backend with oauth2 provider "github" for a blood pressure app - design. Generate unit test with jest and ui test with playwright. 
Multi Language app with de.json and en.json
Use best practice. Generate the style for the app from the provided dark and light image. Ask if some prompts are not clear. 
Tech stack: vite, vitepwa, vite-plugin-mkcert for https, tailwind.
Backend: pocketbase - use best practice for paging
PWA: add an installation app button to the login page. Could also use offline and synchronize the data if online again.
Design as Admin template with sidebar, header (profile avatar in the right with link to the profile, logout)
1. Login page
2. Dashboard: Quick Entry for the blood pressure. all number input with +- button, last 3 measure (could define and change in the user setting), report for the last month 
3. Measure: Card View and Table view as genericCRUD component to add new records, sorting, filtering. Show "created", "updated" as read-only fields
4. Reports: Filter, Show different charts
5. User Profile: Avatar, Name of the user, all settings like theme mode, default pagesize (default = 10), language stored in the pb.collection('users') -> "settings"

sample:
   "id": "RECORD_ID",
      "collectionId": "_pb_users_auth_",
      "collectionName": "users",
      "username": "username123",
      "verified": false,
      "emailVisibility": true,
      "email": "test@example.com",
      "created": "2022-01-01 01:00:00.123Z",
      "updated": "2022-01-01 23:59:59.456Z",
      "name": "test",
      "avatar": "filename.jpg",
      "settings": "JSON"
6. FAQ

Pocketbase collection:

- pb.collection('users')


- blood_pressure_readings
  "id": "RECORD_ID",
      "collectionId": "yqm401sdl7m876p",
      "collectionName": "blood_pressure_readings",
      "created": "2022-01-01 01:00:00.123Z",
      "updated": "2022-01-01 23:59:59.456Z",
      "user_id": "RELATION_RECORD_ID",
      "systolic": 123,
      "diastolic": 123,
      "pulse": 123,
      "timestamp": "2022-01-01 10:00:00.123Z",
      "notes": "test"


# 2024-11-29: Perplexity Answer 

## Testing

1. Write unit tests using Jest for components and utility functions
2. Create UI tests with Playwright for critical user flows

## Performance Optimization

1. Implement code splitting and lazy loading for better performance
2. Optimize images and assets for faster loading

## GDPR Compliance

1. Implement necessary consent mechanisms
2. Create a privacy policy page
3. Allow users to download or delete their data

## Security

1. Implement proper input validation and sanitization
2. Use secure HTTP-only cookies for session management
3. Implement rate limiting on the backend

## Accessibility

1. Ensure proper keyboard navigation
2. Add ARIA attributes for better screen reader support
3. Maintain sufficient color contrast for all themes

Remember to follow React and TypeScript best practices throughout the development process. Use custom hooks for reusable logic, and implement proper state management using React Context or a state management library if needed.

Citations:
[1] https://dev.to/tigawanna/social-app-with-react-and-pocketbase-oauth-authentication-1nb7
[2] https://github.com/pocketbase/pocketbase/discussions/2286
[3] https://github.com/pocketbase/pocketbase/discussions/3563
[4] https://github.com/rajesh6161/pocketbase-oauth-demo
[5] https://github.com/pocketbase/pocketbase/discussions/2429
[6] https://github.com/iamelevich/pocketbase-plugin-telegram-auth
[7] https://github.com/pocketbase/pocketbase/discussions/3718
[8] https://github.com/benallfree/awesome-pocketbase/blob/main/README.md

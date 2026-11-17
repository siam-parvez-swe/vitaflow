VitaFlow --- Blood Donation Platform Showcase
VitaFlow is a frontend-only blood donation platform prototype built
to demonstrate how a digital community could connect blood donors,
people requesting blood, and volunteers.

The project focuses on the user experience: browsing blood requests,
finding donors, registering with contact information, coordinating
through contact actions, and exploring role-based dashboards.
Project status: UI/UX showcase and browser-based demo only. This
repository does not contain a backend, API server, database, real
authentication service, or real payment processing.

Table of Contents
- Project Overview
- What the Prototype Includes
- User Roles
- Registration, Login, and Donor
  Contact
- Demo Accounts
- How Data Is Stored
- Technology Stack
- Getting Started
- Available Scripts
- Project Structure
- Known Limitations
- Ideas for a Future Production
  Version
- License
Project Overview
The goal of VitaFlow is to present a clear, approachable interface for a
blood donation community.

A visitor can explore the public-facing experience, browse sample blood
requests, search a sample donor directory, and view the funding
contribution interface. A user can also create a local demo account,
sign in, manage a profile, create a blood request, and explore the
dashboard available to their demo role.

The interface is designed to work across desktop, tablet, and mobile
screen sizes.
Main goals
- Make blood requests easy to browse and understand.
- Help users find potential donors by blood group and location.
- Collect a donor's email address and phone number during
  registration.
- Make donor/requester contact options visible in the relevant UI
  flows.
- Demonstrate different dashboard experiences for Admin, Donor, and
  Volunteer roles.
- Keep the project simple to run as a frontend-only showcase.
What the Prototype Includes
Public-facing experience
- Landing page introducing the VitaFlow concept.
- Blood request directory with text search and filters.
- Donor directory with blood group, district, and name/area filters.
- Donor profile/contact modal.
- Funding contribution page with preset and custom amounts.
- Responsive navigation for smaller screens.
Blood request experience
- Create a blood request with:
  - Recipient name
  - Blood group
  - District and area/upazila
  - Hospital name
  - Full address
  - Required date and time
  - Optional message
- Browse request details.
- View request status.
- Edit or delete a user's own requests in the donor dashboard.
- Respond to a pending request using the I can donate action.
- Store the responding donor's demo contact information with the
  request.
- Update request status from the Admin or Volunteer dashboard.
The request statuses used in the interface are:
- pending
- inprogress
- done
- canceled
Donor directory and contact actions
- Search active donor profiles.
- Filter by blood group and district.
- Search by donor name or area.
- Open a donor contact panel.
- Display a donor's phone number and email address when contact
  sharing is enabled.
- Provide these contact actions:
  - Call --- opens the device's phone handler using a tel:
    link.
  - Email --- opens the visitor's configured email application
    using a mailto: link.
  - WhatsApp --- opens a WhatsApp chat link.
  - Viber --- opens a Viber chat link.
These actions hand off to the visitor's device or installed application.
VitaFlow does not send calls or messages itself.
Registration and sign-in
The local demo registration form collects:
- Full name
- Email address
- Phone number
- Password
- Blood group
- District
- Upazila/area
- Contact-sharing preference
New registrations are assigned the Donor role by default.

The sign-in form accepts either an email address or a phone number,
together with the password. This is a browser-side demo flow, not secure
authentication.
Contact privacy preference
A user can choose whether their contact details may be displayed to
signed-in members in the relevant donor/request coordination interfaces.

The preference can be changed from the profile page. This is included to
demonstrate the intended user experience; it is not a security
control because there is no backend enforcing access permissions.
Profile management
The profile interface allows a signed-in demo user to:
- View profile information.
- Update their name, phone number, blood group, district, and area.
- Change the contact-sharing preference.
- Upload a profile image (the UI accepts image files up to 1 MB).
The email field is displayed as read-only in the profile form.
Role-based dashboards
The prototype includes three demo roles.

Donor - View a personal dashboard. - Create blood requests. - View
personal requests. - Edit or delete personal requests. - Browse the
public request list and donor directory. - Respond to pending requests.

Volunteer - View the dashboard overview. - Browse all blood
requests. - Update request statuses. - View the donor directory and
public funding interface.

Admin - View the dashboard overview. - Browse and update all blood
requests. - View user records. - Change a user's demo role. - Block or
unblock demo users. - View the locally recorded funding entries.

Role-specific navigation and screens are part of the frontend
demonstration. They are not protected by server-side authorization.
Funding interface
- Preset contribution amounts: $5, $10, $25, $50, and $100.
- Custom contribution amount.
- Local demo contribution confirmation.
- Recent contribution list.
- Admin view of locally recorded contribution entries.
No payment is processed. The interface simulates a contribution and
stores a demo record in browser storage. It does not connect to Stripe
or any payment gateway.
User Roles
  Role                                Main demo capabilities
  Donor                               Create and manage own requests,
respond to pending requests, browse
donors and requests

  Volunteer                           View all requests and update
request statuses
Admin                               Manage demo users and roles, update
all requests, view funding records
The registration form creates Donor accounts. The Admin and Volunteer
experiences can be explored using the seeded demo accounts listed below.
Registration, Login, and Donor Contact
The intended prototype flow is:
1. A visitor opens the registration form.
2. They provide their name, email address, phone number, password,
   blood group, and location.
3. They choose whether to share their contact details with signed-in
   members.
4. The new Donor profile is stored in the current browser's local
   storage.
5. A signed-in user opens the donor directory and searches by blood
   group or location.
6. Selecting Contact donor opens the donor's contact panel.
7. If the donor has enabled contact sharing, the panel displays the
   available phone/email details and relevant contact actions.
8. A donor can also respond to a pending blood request. The demo
   request is updated to inprogress, and the responding donor's
   contact details are attached to that request's local data.
9. The requester can view the connected donor details in the request
   detail panel, subject to the donor's contact-sharing preference.
The prototype includes basic form validation and duplicate email/phone
checks against data stored in the current browser. These checks are not
a replacement for server-side validation.
Demo Accounts
The following sample accounts are included for exploring the
role-specific interfaces.

Password for all seeded demo accounts: demo1234

  Role        Email                       Sample phone
  Admin       admin@vitaflow.demo       +880 1XXX-XXX-100
Donor       donor@vitaflow.demo       +880 1XXX-XXX-101
Volunteer   volunteer@vitaflow.demo   +880 1XXX-XXX-102

The sample phone numbers are intentionally masked placeholders. Contact
actions are disabled for seeded demo profiles so that the showcase does
not accidentally initiate contact with a real person.

To demonstrate the Call, Email, WhatsApp, and Viber actions, register a
new test account using contact details that you control and enable
contact sharing.
How Data Is Stored
VitaFlow currently uses the browser's localStorage for demo
persistence.

The application stores these demo data categories:

  Local storage key     Purpose
  vitaflow_users      Seeded and newly registered demo user profiles
vitaflow_requests   Sample and locally created blood requests
vitaflow_fundings   Simulated contribution records
vitaflow_session    Current demo session identifier
What this means
- Data is saved only in the browser profile and origin where the demo
  is running.
- Data is not shared with other visitors or devices.
- A different browser or device has a separate local data set.
- Clearing the website's browser storage removes the locally saved
  demo data and session.
- Seed data is included in the frontend source code.
- There is no remote database or API synchronization.
For a clean demo, clear the site's local storage in the browser's
developer tools and reload the page. This resets locally stored changes
and restores the seeded sample state.
Technology Stack
  Technology                          Use
  Next.js      React framework and App Router
14.2.35                             

  React 18.3.1  UI components and client-side state

  Lucide React Interface icons
0.468.0                             

  CSS                                 Custom styling and responsive
layouts

  Browser localStorage              Local demo persistence
ESLint                              Code linting
The main interactive experience is implemented as a client-side React
component in app/page.jsx. Styling is maintained in app/globals.css.
No backend services are included
This repository does not currently include or connect to:
- Node.js/Express API server
- MongoDB or another database
- Better Auth, Firebase Auth, or another authentication provider
- JWT-based server authentication
- Stripe or another payment processor
- Email/SMS notification service
- Image hosting service
- Remote file storage
No environment variables are required to run the current frontend
showcase. The .env.example file contains placeholder configuration
examples only; the current demo does not require those values.
Getting Started
Requirements
- Node.js 18.17 or newer
- npm
1. Clone the repository
Replace the placeholder URL with the URL of your GitHub repository.
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd vitaflow-showcase
2. Install dependencies
npm install
3. Start the development server
npm run dev
Open http://localhost:3000 in your browser.
4. Create a production build
npm run build
5. Run the production build locally
npm start
The production server starts after a successful build.
Available Scripts
  Command           Description
  npm run dev     Start the Next.js development server
npm run build   Create a production build
npm start       Run the production server
npm run lint    Run the Next.js ESLint command

There is no automated test script configured in the current
package.json.
Project Structure
vitaflow-showcase/
├── app/
│   ├── globals.css       # Global styles, components, and responsive layouts
│   ├── layout.jsx        # Root layout and page metadata
│   └── page.jsx          # Main client-side VitaFlow experience
├── public/
│   └── favicon.svg       # Application favicon
├── .env.example          # Placeholder environment examples; not required
├── .eslintrc.json        # ESLint configuration
├── .gitignore
├── LICENSE
├── next.config.mjs       # Next.js configuration
├── package.json
└── README.md
Known Limitations
VitaFlow is a portfolio and project-showcase prototype. It should not be
used as a live blood donation or medical coordination service.
Authentication and security
- Registration and sign-in are simulated in client-side JavaScript.
- Passwords are stored in browser local storage as ordinary
  client-side data; they are not securely hashed.
- There is no server-side session management, identity verification,
  or authorization.
- Demo role restrictions are implemented in the interface and can be
  bypassed by modifying browser-side data.
- Contact-sharing preferences are presentation logic only; they do not
  protect personal information from someone inspecting the browser.
Do not enter real passwords, sensitive personal information, or
confidential patient information.
Data and availability
- Local data is not synchronized between visitors or devices.
- There is no real-time update system.
- Sample donors and blood requests are illustrative records, not
  verified people or active medical requests.
- The figures, charts, trends, and impact counters shown in the
  interface are illustrative showcase content, not measured platform
  statistics.
Contact actions
- Call, Email, WhatsApp, and Viber actions depend on the visitor's
  device and installed applications.
- The application does not send messages, verify delivery, or record
  successful contact.
- Seeded demo phone numbers are masked and their contact actions are
  disabled.
Funding
- Contributions are simulated locally.
- No real payment, card processing, transaction verification, or
  financial transfer takes place.
- A locally generated demo transaction reference is not a payment
  receipt.
Medical and operational use
- Donor eligibility, blood-group compatibility, identity,
  availability, hospital information, and request details are not
  verified.
- The interface does not provide medical advice or emergency response
  services.
- Always use appropriate medical and institutional procedures for real
  blood donation coordination.
Ideas for a Future Production Version
The following items are not implemented in this repository. They are
possible next steps if the prototype is later developed into a real
service:
- A secure backend API and database.
- Server-side authentication, password hashing, and role-based
  authorization.
- Email and phone verification.
- Consent-aware contact information access enforced by the backend.
- Request ownership checks and audit history.
- Real payment integration with server-side payment verification.
- Email/SMS notifications.
- Abuse reporting, moderation, and account recovery.
- Verified donor and hospital workflows.
- Privacy, data-retention, and security policies appropriate to the
  operating region.
License
This project is distributed under the MIT License. See the
LICENSE file for details.

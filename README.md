# VitaFlow — Blood Donation Platform Showcase

VitaFlow is a responsive, frontend-only prototype that demonstrates how a blood donation community platform can connect donors, recipients and volunteers. It is built with Next.js 14 (App Router), React and custom CSS.

## Showcase features

- Responsive landing page and public blood-request directory
- Donor directory with blood-group, district, name and area filters
- Registration collects name, email, phone number, blood group and location
- Sign-in accepts either email address or phone number
- Donor contact panel with Call, Email, WhatsApp and Viber actions
- Contact details are shown only when the member has enabled contact sharing
- Users can change contact details and contact-sharing preference from their profile
- Request details show requester contact information to signed-in members who are allowed to view it
- When a donor responds to a request, their contact details are attached to the demo request so the requester can coordinate directly
- Admin, Donor and Volunteer demo roles with role-specific dashboards
- Local demo blood requests, donor profiles, funding records and profile editing
- Browser persistence through `localStorage`
- Mobile, tablet and desktop responsive layouts

## Run locally

Requirements: Node.js 18.17+ and npm.

```bash
npm install
npm run dev
```

Open <http://localhost:3000>.

To create a production build:

```bash
npm run build
npm start
```

## Demo accounts

All demo accounts use the password `demo1234`.

| Role | Email | Phone shown in demo |
|---|---|---|
| Admin | `admin@vitaflow.demo` | `+880 1XXX-XXX-100` |
| Donor | `donor@vitaflow.demo` | `+880 1XXX-XXX-101` |
| Volunteer | `volunteer@vitaflow.demo` | `+880 1XXX-XXX-102` |

The demo phone numbers are intentionally masked placeholders. Call, Email, WhatsApp and Viber actions are disabled for seeded demo profiles so the showcase cannot accidentally contact a real person. Register a test user with your own test contact details to demonstrate those actions.

## How contact sharing works in the prototype

1. A new member registers with both an email address and a phone number.
2. The member can choose whether signed-in members may view those contact details.
3. The donor directory displays the phone number or a privacy message.
4. Selecting **Contact donor** opens a contact panel with Call, Email, WhatsApp and Viber actions when the member has shared valid contact details.
5. When a donor responds to a blood request, their contact details are attached to that request in the local demo state. The requester can view the donor's details in the request panel.

## Demo mode and important limitations

This project intentionally has no backend or database. User accounts, passwords, requests and funding entries are stored in the current browser's `localStorage` only. Data is not synchronized between devices or different visitors, and clearing browser storage resets the local demo.

This is a portfolio/showcase prototype, not a production medical or identity system:

- Authentication is simulated in the browser. Passwords are not securely hashed and must never be used for real accounts.
- Contact details are not protected by a server-side access-control layer. The sharing preference is a UI demonstration, not a security boundary.
- Call opens the phone dialer; WhatsApp and Viber open their respective apps when installed; Email opens the visitor's mail app. The prototype does not send messages itself.
- Funding is simulated. No real payment is collected.
- Demo requests and donor records are sample data, not live medical requests or verified donors.

A production release would require a secure backend, database, server-side authorization, phone/email verification, abuse reporting, consent management and appropriate privacy safeguards.

## Project structure

```text
vitaflow-showcase/
├── app/
│   ├── globals.css
│   ├── layout.jsx
│   └── page.jsx
├── public/
│   └── favicon.svg
├── .env.example
├── .gitignore
├── next.config.mjs
├── package.json
└── README.md
```

## Technology

- Next.js 14.2
- React 18
- Lucide React icons
- Custom responsive CSS
- Browser `localStorage` for demo persistence

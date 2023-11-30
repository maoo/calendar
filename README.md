# FINOS Calendar

This code builds the page hosted on https://calendar.finos.org , which is also embedded on https://www.finos.org/calendar , in order to provide a fully hosted solution that shows all events in the [FINOS Community (Google) Calendar](https://calendar.google.com/calendar/embed?src=symphony.foundation_6g70j7s80813djmj9q7gmgdjuc%40group.calendar.google.com&ctz=Europe%2FMadrid) that can be correctly visualised also behind a corporate firewall.

A Github action runs periodically to fetch events using Google APIs (see [src/googleapi2events.js](src/googleapi2events.js)) and renders out a JSON file in `dist/events.json`.

The calendar is visualized in HTML using React and [FullCalendar](https://fullcalendar.io/).

## Prerequisites

- Node.js and npm installed on your machine.
- `gpg`

## Getting Started (work in progress, see https://github.com/finos/calendar/issues/9 )

1. Clone the repository:

```bash
git clone https://github.com/finos/calendar.git
cd calendar
```

2. Download `calendar-service-account.json` into the project's root folder.

TODO: add link to docs on how to download calendar-service-account.json

### Encrypting Google Service Account key

```
gpg --symmetric --cipher-algo AES256 calendar-service-account.json
```

### Install the dependencies:

```bash
npm install
```

### Run development server

```bash
npm run dev
```

Open browser to `http://localhost:5173/`.
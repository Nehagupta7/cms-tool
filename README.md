# Relay Save/Publish Tool

A single-file HTML utility for sending **Save** and **Publish** payloads to your backend via
curl-style requests, with a built-in visual JSON editor so you don't have to hand-edit raw,
lengthy JSON in a plain textarea.

Open `relay-save-publish-tool.html` directly in any browser — no build step, no server, no
dependencies.

---

## What it does

- Two independent panels: **Save** and **Publish**, each with its own request (curl paste or
  manual URL/headers) and a JSON payload box.
- Requests are sent from the browser; responses are shown inline.
- Save/Publish setup and payloads persist in the browser between sessions.
- Publish payload auto-fills from Save's result + content ID once Save succeeds.

## The JSON editor ("Format & edit")

Long, deeply-nested JSON (like a page's `sections` payload with FAQ categories and questions)
is hard to eyeball or hand-edit in a textarea. Click **Format & edit** next to either payload
box to open a side panel with a structured, editable tree view of that JSON.

### Viewing
- Objects and arrays render as collapsible nodes with a `{n}` / `[n]` count.
- Long objects/arrays (more than 4 entries) start **collapsed automatically** so you see
  structure first, detail on demand.
- Each collapsed node shows a **preview** of an identifying field so you know what's inside
  without expanding it — e.g. `Object {5} — faq-block`, `Array [11] — About Champions`,
  `Array [7] — What is Champions?`. It looks for (in order): `type`, `name`, `title`,
  `question`, `label`, `key`, `id`; for arrays of plain strings/numbers it previews the first
  value.
- A **search box** filters the tree by key or value and auto-expands matching branches — handy
  for jumping straight to something like "SellProof" in a large FAQ payload.

### Editing
- **Rename** any object key inline.
- **Change type** of any value via a dropdown (string / number / boolean / null / object / array).
- **Edit values** directly in text/number inputs or a true/false selector for booleans.
- **Remove** (`×`) any field or item.
- **Add** a single blank field/item ("+ add field" / "+ add item").
- **Paste JSON** ("+ paste JSON") — for when you're adding more than one key at once:
  - Into an **array**: paste a single object to add it as one new item, or paste an array of
    objects to add several at once in one go.
  - Into an **object**: paste an object like `{"status": "draft", "locale": "en"}` and its
    fields get merged in (name clashes get a `_1` suffix rather than overwriting).
  - Invalid JSON shows an inline error and keeps what you typed so you can fix it.
- **Reorder array items**:
  - `↑` / `↓` move an item up or down (greyed out at the start/end).
  - `+` on an item inserts a new blank item directly before it — click it on the first item to
    add something at the very front.

### Applying changes
- **Apply changes** pretty-prints the edited JSON back into the original textarea and closes
  the panel.
- **Cancel** / the **×** close button / clicking outside the panel discards edits without
  touching the textarea.
- If the textarea's current text isn't valid JSON when you open the editor, the panel tells you
  what's wrong and offers to start fresh with an empty object.

---

## Notes

- The editor works on **whatever JSON is currently in the box** — it isn't hardcoded to any one
  payload shape, so it works for Save, Publish, or any future payload structure the same way.
- Editing happens entirely in memory until you click **Apply changes**; nothing is sent to the
  server until you use the tool's normal Save/Publish send buttons.# Relay Save/Publish Tool

A single-file HTML utility for sending **Save** and **Publish** payloads to your backend via
curl-style requests, with a built-in visual JSON editor so you don't have to hand-edit raw,
lengthy JSON in a plain textarea.

Open `relay-save-publish-tool.html` directly in any browser — no build step, no server, no
dependencies.

---

## What it does

- Two independent panels: **Save** and **Publish**, each with its own request (curl paste or
  manual URL/headers) and a JSON payload box.
- Requests are sent from the browser; responses are shown inline.
- Save/Publish setup and payloads persist in the browser between sessions.
- Publish payload auto-fills from Save's result + content ID once Save succeeds.

## The JSON editor ("Format & edit")

Long, deeply-nested JSON (like a page's `sections` payload with FAQ categories and questions)
is hard to eyeball or hand-edit in a textarea. Click **Format & edit** next to either payload
box to open a side panel with a structured, editable tree view of that JSON.

### Viewing
- Objects and arrays render as collapsible nodes with a `{n}` / `[n]` count.
- Long objects/arrays (more than 4 entries) start **collapsed automatically** so you see
  structure first, detail on demand.
- Each collapsed node shows a **preview** of an identifying field so you know what's inside
  without expanding it — e.g. `Object {5} — faq-block`, `Array [11] — About Champions`,
  `Array [7] — What is Champions?`. It looks for (in order): `type`, `name`, `title`,
  `question`, `label`, `key`, `id`; for arrays of plain strings/numbers it previews the first
  value.
- A **search box** filters the tree by key or value and auto-expands matching branches — handy
  for jumping straight to something like "SellProof" in a large FAQ payload.

### Editing
- **Rename** any object key inline.
- **Change type** of any value via a dropdown (string / number / boolean / null / object / array).
- **Edit values** directly in text/number inputs or a true/false selector for booleans.
- **Remove** (`×`) any field or item.
- **Add** a single blank field/item ("+ add field" / "+ add item").
- **Paste JSON** ("+ paste JSON") — for when you're adding more than one key at once:
  - Into an **array**: paste a single object to add it as one new item, or paste an array of
    objects to add several at once in one go.
  - Into an **object**: paste an object like `{"status": "draft", "locale": "en"}` and its
    fields get merged in (name clashes get a `_1` suffix rather than overwriting).
  - Invalid JSON shows an inline error and keeps what you typed so you can fix it.
- **Reorder array items**:
  - `↑` / `↓` move an item up or down (greyed out at the start/end).
  - `+` on an item inserts a new blank item directly before it — click it on the first item to
    add something at the very front.

### Applying changes
- **Apply changes** pretty-prints the edited JSON back into the original textarea and closes
  the panel.
- **Cancel** / the **×** close button / clicking outside the panel discards edits without
  touching the textarea.
- If the textarea's current text isn't valid JSON when you open the editor, the panel tells you
  what's wrong and offers to start fresh with an empty object.

---

## Notes

- The editor works on **whatever JSON is currently in the box** — it isn't hardcoded to any one
  payload shape, so it works for Save, Publish, or any future payload structure the same way.
- Editing happens entirely in memory until you click **Apply changes**; nothing is sent to the
  server until you use the tool's normal Save/Publish send buttons.

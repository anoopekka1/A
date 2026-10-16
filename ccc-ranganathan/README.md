# CCC Study Desk — Ranganathan

A small, static, mobile-friendly study/practice app for S. R. Ranganathan's *Classified Catalogue Code*, 5th edition (1960), using the chapter/part structure visible in the user's uploaded scan.

## Run it
Open `index.html` in a browser, or publish this folder using GitHub Pages (repository Settings → Pages, select the branch and `/ (root)` or move this folder's files to root if desired). This is a static HTML/CSS/JavaScript app; no build step is required.

## Features
- Parts A–W and chapter-wise topic selection, matching the contents page
- Unified single-question practice view; selected-chapter and mixed practice
- Progressive hints, answer feedback, explanations, and source-location notes
- Bookmarks, retry incorrect questions, and local progress summary
- Responsive design and local browser storage

## Content and source discipline
The uploaded source identifies this as *Classified Catalogue Code with additional rules for Dictionary Catalogue Code*, S. R. Ranganathan, 5th edition (1960). Chapter list is transcribed from its contents (PDF pages 10–17 / printed pages 7–14). The five laws are taken from PDF page 9. Every seeded question has a short reference note. The initial bank emphasizes source-verifiable details such as book structure and the introductory chapters; it is not yet a comprehensive question bank for every substantive cataloguing rule. Add questions only after checking the corresponding source pages. Never use a guessed page/rule reference.

## Extend the question bank
In `index.html`, update the `QUESTIONS` array. Each question has:
```js
{
  id: "unique-id",
  part: "B",
  chapter: "BB",
  topic: "Canon of Ascertainability",
  level: "Foundation",
  q: "Question text",
  options: ["Option A", "Option B", "Option C", "Option D"],
  a: 0,
  hints: ["Gentle clue", "More specific clue"],
  explanation: "Source-grounded explanation",
  ref: "PDF page ...; printed page ... · Chapter ...",
  supported: true
}
```
`a` is the zero-based index of the correct option. Provide two progressive hints. Use the exact chapter code shown in the contents.

## GitHub as content backend
This first version is a GitHub-hosted, version-controlled static app; the question bank is bundled in `index.html` and updates are committed to the repository. It does **not** call GitHub API from the browser and does not require a token. This avoids exposing a private token in client code. Study attempts/bookmarks live in that browser's localStorage and are not synced to GitHub. Cross-device user accounts/progress would need a secure server/API or an authenticated backend; don't place a GitHub token in frontend JavaScript.

## Current scope
- App UI and study interactions are implemented.
- Chapter structure covers the parts listed in the scanned contents.
- Sample practice questions are included, with references where verified.
- Comprehensive rules/examples coverage should be added topic by topic after checking the source.

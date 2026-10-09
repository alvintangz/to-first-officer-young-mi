To First Officer Young-mi

Run locally:
1. Extract this folder.
2. Open a terminal in the folder and run: python3 -m http.server 8000
3. Open http://localhost:8000 in your browser.

The site loads flashcards.json through HTTP. Opening index.html directly as a
file will not work in browsers that block local JSON requests.
To deploy, put index.html and flashcards.json together on any static web host.

All title, category metadata, study notes, source links, topics and cards live
in flashcards.json. No content is embedded in the application JavaScript.
Add another object to the categories array to add a deck:

{
  "id": "unique-category-id",
  "name": "Category name",
  "description": "Short description",
  "studyHint": "Optional study tip",
  "source": {
    "note": "Optional source note",
    "label": "Study source",
    "url": "https://example.com"
  },
  "cards": [
    { "topic": "Topic name", "question": "Question?", "answer": "Answer." }
  ]
}

The category and topic menus are generated automatically from that JSON.
Changing either menu starts a new round. Shuffle, tap-to-reveal, Got it,
Study again, and review-missed-cards retain the original behavior.

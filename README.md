# Study Portal

Five subjects, 61 chapters, 311 topics, 1052 resource links — one dark, searchable interface.

## Opening it

Double-click **`index.html`**, or open any subject file directly:

| File | Subject | Accent |
|---|---|---|
| `index.html` | All five subjects | — |
| `physics.html` | Physics · 14 chapters · 70 topics | jade |
| `chemistry.html` | Chemistry · 8 chapters · 38 topics | amber |
| `maths-1a.html` | Mathematics 1A · 10 chapters · 43 topics | violet |
| `maths-1b.html` | Mathematics 1B · 10 chapters · 63 topics | azure |
| `biology.html` | Biology · 19 chapters · 97 topics | leaf |

Every file is self-contained — styles, data and scripts are inside the page.
Nothing to install, no folder structure to preserve. Send one file to a friend
and it still works.

**Biology is a special case.** It was built as its own standalone "field
notes" page before the shared portal engine existed, with a different look
(leaf-green theme), multi-part video links, and chapter-wide MCQ links on
some chapters. Rather than force it through the shared search/filter engine
and risk losing that structure, it's linked in as-is from the home page — the
home card, accent colour and chapter/topic/resource counts are wired in, and
a "Study Portal" link at the top of the page takes you back to `index.html`.
It doesn't have the search box, filter chips, or done-checkboxes the other
four subjects have.

## Using a subject page

- **Search** — click the box or press `/`. Matches chapter names, topic names,
  descriptions, and topic numbers like `4.2`. Press `Esc` to clear.
- **Filter chips** — tap any resource type (Video, Slides, MCQs, and so on) to
  show only topics that have it. Chemistry's chips read Images, Video, Slides,
  Mind map, MCQs — the other three subjects use Video, Slides, Mind map, Notes,
  MCQs. Tap a chip again to turn it off; combine them freely.
- **Chapter rail** — the list on the left jumps to a chapter and highlights
  where you are as you scroll. Hidden on narrow screens.
- **Checkboxes** — tick a topic when you've finished it. The bar at the top and
  the count on each chapter update as you go.
- **Resourced %** — on each chapter header, how much of the expected material
  is actually uploaded. Dashed "soon" pills mark the gaps.

Progress is stored in your own browser. It won't follow you to another device,
and clearing site data will reset it.

## Known gaps in the source material

These came across from the original portals and are shown honestly rather than
hidden:

- Chemistry has no chapter 7, and chapter 6 topics are titled "Advanced Topic 1–4".
- Chemistry topic 5.3 (Extensive and Intensive Properties) has no resources yet.
- Chemistry chapter 8 topics 8.2–8.6 have MCQs only — no video, slides or images.
- Chemistry's resource types differ from the other three subjects: its former
  "Notes" and generic "Material 2 / Material 3" links are now organised as
  Video, Slides and Images (in that order), plus MCQs and, for chapter 6 only,
  a Mind map.
- Physics has no slides; Mathematics 1B has no mind maps.
- Biology's video resource is sometimes split into several "Part" links
  instead of one — the coverage numbers on the home page count that as a
  single resource, same as every other kind.
- Biology's Online Mock Test column is entirely empty so far ("Coming soon"
  on every topic), and 150 MCQ PDF is only filled in for some chapters.

## Changing links

Open the subject file in a text editor and search for `window.PORTAL_DATA`.
Each topic looks like this:

```js
{ "num": "9.1", "title": "Introduction & First Principle", "desc": "...",
  "res": { "video": "https://...", "slides": "https://...",
           "notes": "https://...", "mcq": "https://...",
           "test": null, "extra": [] } }
```

Paste a URL in place of `null` to fill a gap; set a URL to `null` to hide it.
Save, refresh the page.

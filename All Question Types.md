# Playable Quizzes — All Question Types

A single quiz demonstrating every supported question type. Paste into a vault
with **Playable Quizzes** enabled. Try it in both `one-at-a-time` and
`all-at-once` modes (change `mode:` below), then submit, review feedback, and
retry.

```playable-quiz
quiz:
  id: everything
  title: One Quiz, Every Type
  description: Multiple-choice, true/false, multiple-select, reorder, matching, short-text, and numeric.
  mode: all-at-once
  passingScore: 60
  persistAnswers: true
  questions:
    - id: q1
      type: multiple-choice
      prompt: Which service was primarily used to subscribe to RSS feeds?
      options:
        - id: a
          text: GeoCities
        - id: b
          text: Google Reader
        - id: c
          text: Napster
      correctAnswer: b
      points: 1
      explanation: Google Reader was a popular RSS reader.

    - id: q2
      type: true-false
      prompt: StumbleUpon was used for website discovery.
      correctAnswer: true
      points: 1

    - id: q3
      type: multiple-select
      prompt: Which of these are web browsers?
      options:
        - id: firefox
          text: Firefox
        - id: chrome
          text: Chrome
        - id: obsidian
          text: Obsidian
        - id: vscode
          text: Visual Studio Code
      correctAnswers:
        - firefox
        - chrome
      scoring: all-or-nothing
      points: 2

    - id: q4
      type: reorder
      prompt: Put these web eras in chronological order.
      items:
        - id: static-web
          text: Static personal homepages
        - id: social-web
          text: Social networking platforms
        - id: mobile-web
          text: Mobile-first platforms
      correctOrder:
        - static-web
        - social-web
        - mobile-web
      points: 2

    - id: q5
      type: matching
      prompt: Match each service with its purpose.
      prompts:
        - id: reader
          text: Google Reader
        - id: aim
          text: AIM
        - id: geocities
          text: GeoCities
      choices:
        - id: rss
          text: RSS subscriptions
        - id: chat
          text: Instant messaging
        - id: hosting
          text: Personal website hosting
      correctMatches:
        reader: rss
        aim: chat
        geocities: hosting
      points: 3

    - id: q6
      type: short-text
      prompt: What does RSS stand for?
      acceptedAnswers:
        - Really Simple Syndication
        - RDF Site Summary
      caseSensitive: false
      trimWhitespace: true
      points: 1

    - id: q7
      type: numeric
      prompt: How many bits are in one byte?
      correctAnswer: 8
      tolerance: 0
      points: 1
```

## Notes on interaction

- **Multiple-select** uses checkboxes; order of selection does not matter.
- **Reorder** uses accessible **▲ / ▼** buttons (works on mobile). The order
  shown is what gets submitted if you do not move anything.
- **Matching** uses dropdowns; a choice already used by another prompt is
  disabled to keep matches one-to-one.
- **Short-text** is case-insensitive and trims whitespace by default.
- **Numeric** accepts a number within the configured `tolerance` (0 here).

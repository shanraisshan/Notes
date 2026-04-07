# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A personal knowledge base / wiki of technical notes organized as a hierarchy of Markdown README.md files. There is no source code to build, test, or lint. The repository was created on 26 Jan 2022.

## Repository Structure

- Each top-level directory is a topic category (e.g., `AI/`, `App/`, `Architecture/`, `Language/`)
- Subdirectories nest further subtopics; every directory contains a `README.md` as its entry point
- Images and assets live in `!/` subdirectories alongside their README (e.g., `App/Android/Design/!/dp-banner.png`)
- The root `README.md` is the table of contents linking to all top-level categories

## Formatting Conventions

These conventions are used consistently throughout the notes and must be followed when editing or adding content:

- **Section links** use the arrow prefix: `### ➼ [Title](path)`
- **Subtopic qualifiers** go in parentheses after the title: `➼ Link (+App, Deep, Dynamic, Universal) 🔗`
- **Hyperlink references** within notes use `-> details` pattern: `[-> details](Language/Kotlin/README.md#function)`
- **Separators**: `■` and `•` for bullet separators, `->` as secondary separator
- **Links tables** use a centered markdown table format:
  ```
  Description|Link
  :-:|:-:
  description text|https://example.com
  ```
- **Image sizing**: referenced in commit/asset naming as dimensions like `600x282`
- Emoji icons are used in section headers to visually distinguish categories

## When Adding or Editing Notes

- Place content in the appropriate topic directory; create a new subdirectory with a `README.md` if the topic doesn't exist yet
- Follow the existing `### ➼ [Title](path)` link style when adding navigation entries
- Keep the root `README.md` updated if adding a new top-level category

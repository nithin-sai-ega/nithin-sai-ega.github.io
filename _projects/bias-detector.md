---
layout: page
title: Bias Detector
description: Chrome extension that checks articles and text for political bias and fake-news likelihood
importance: 4
summary: A Chrome extension with a Spring Boot backend that sends a webpage, URL, or pasted text to Google's Gemini model and shows its political-bias direction and fake-news estimate.
tech:
  - Java
  - Spring Boot
  - JavaScript
  - Chrome Extension
  - Gemini API
---

**Java, Spring Boot, JavaScript, Chrome Extension (Manifest V3), Google Gemini API** · Built for HackRU 2025 · [Source on GitHub](https://github.com/nithin-sai-ega/bias-detector-hackathon-project)

- Built a Chrome extension (Manifest V3) whose popup analyzes the current webpage, a pasted URL, or pasted text; a content script extracts the page's readable text.
- Developed a Spring Boot REST backend with `/analyze/text` and `/analyze/url` endpoints; for URLs it fetches the article with Jsoup.
- Prompts Google's Gemini 2.0 Flash model and parses its JSON reply into a bias direction (left, right, or neutral, with a confidence percentage), a fake-news percentage, and a written explanation.
- Shows the results in the popup as a fake-news level, a bias label and score, and the model's reasoning.

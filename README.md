# AI-900 Practice Exam Dashboard

An interactive, web-based dashboard designed to help you prepare for the Microsoft Azure AI Fundamentals (AI-900) exam. This application reads question banks stored in Markdown (`.md`) or text (`.txt`) formats and presents them in an easy-to-use, interactive quiz interface with immediate feedback.

## Features

- Parse standard text and Markdown files for questions.
- Compatible with common practice exam export formats.
- Interactive web UI built with HTML, CSS, and Vanilla JavaScript.
- Clean, responsive design with Dark/Light modes.
- Session autosaving allows you to resume progress later.

## Getting Started

1. Clone or download this repository.
2. Place your question bank files (e.g., `questions.md`, `practice-exam.txt`) in the root directory.
   *(Note: Question bank files are excluded in `.gitignore` by default. This repo contains only the dashboard tooling, not any exam content.)*
3. Open `exam-hub.html` or `ai900-dashboard.html` in your web browser. No local web server is required for basic usage.

## Question Formatting

To learn how to format your own question banks so the dashboard can parse them properly, please consult the [`exam_format_guide.md`](exam_format_guide.md) file included in this repository.

## Utilities

A `tools/` folder contains Python scripts that can generate HTML from templates, fix formatting, and apply bulk patches to your local dashboard:
- `generate_exam.py`
- `patch_*.py`
- `fix_classlist.py`

*(Note: You'll require Python 3 if you wish to run these builder/utility scripts.)*

## ⚠️ Legal Disclaimer

This project provides **tooling only** — it does not include, distribute, or endorse any exam content.

- Users are solely responsible for ensuring any question banks they use comply with applicable exam NDAs, certification program terms, and copyright law.
- Do not use this tool with actual exam questions, exam dumps, or any material obtained in violation of an exam Non-Disclosure Agreement.
- This tool is intended only for legitimate practice questions from authorized sources or user-created content.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

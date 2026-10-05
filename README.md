# Wording Check

A single-file web tool that highlights gender-coded wording in job keywords and anonymized resume text, so a recruiter can take a second look. It flags wording only. It does not score candidates or make hiring decisions.

## Features

- Paste job keywords and anonymized resume text
- Highlights masculine-coded and feminine-coded words in the text
- Shows a risk badge (Low, Medium, High), a flagged-phrase count, and a masculine/feminine split
- Lists each unique flagged word with its category
- Built-in biased and neutral sample texts for demos
- Light and dark mode, and a layout that works on phones

## How to Run

1. Save the code as `index.html`.
2. Open the file in any modern web browser.

No install, build step, or server is needed. The page loads the Public Sans font from Google Fonts and falls back to system fonts if it is offline.

## How to Use

1. Enter job keywords in the first box.
2. Paste anonymized resume text in the second box.
3. Click **Run Wording Check**.
4. Review the highlighted phrases and the risk badge.

Use **Load biased sample** or **Load neutral sample** to see example results. Use **Clear** to reset.

## How It Works

The tool matches the pasted text against two word lists using case-insensitive regular expressions.

- **Masculine-coded list:** for example aggressive, dominant, ninja, rockstar, competitive, chairman, salesman
- **Feminine-coded list:** for example supportive, nurturing, collaborative, empathetic, loyal

Risk level is based on the total number of flagged phrases:

| Flagged phrases | Risk level | 
| 0 to 1 | Low |
| 2 to 4 | Medium |
| 5 or more | High |

## Customizing

To change which words are flagged, edit the `M` (masculine-coded) and `F` (feminine-coded) arrays near the top of the `<script>` section. Each entry is a regular expression fragment, so `"collaborat\\w*"` matches collaborate, collaborative, collaboration, and so on.

To change the risk thresholds, edit the line that sets `lvl`.

## Limitations

- It is a keyword matcher. It has no understanding of context, so a flagged word is not necessarily biased.
- The word lists are short and simplified. They are not a validated research instrument.
- It only checks wording. It does not detect other sources of bias.
- English only.

## Privacy and Responsible Use

- Everything runs in the browser. Nothing is sent to a server or stored.
- Use only synthetic or anonymized text. Do not paste real applicants' personal information.
- Results are informational. A person should always make the final decision.

## Tech

HTML, CSS, and vanilla JavaScript in one file, with no dependencies.

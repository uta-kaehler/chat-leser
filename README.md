# Chat-Leser

**A reader for Claude and ChatGPT data exports: find one conversation among hundreds, read it by day, and keep it, with a consent header if you need one.**

Open it here: **[uta-kaehler.github.io/chat-leser](https://uta-kaehler.github.io/chat-leser/)** (best on a computer)

The interface is in German.

## Why

AI providers let you download your data, but the result is one large file in which every conversation is mixed with
every other. Long conversations that run for months start on different days, and there is no way to see which is which.
The Chat-Leser turns that file back into conversations.

## What it does

| | |
| --- | --- |
| Open | The export as it arrives (ZIP) or the unpacked JSON. Several files can be added; nothing is replaced, conversations that are already there are updated |
| List | All conversations with start date, last activity and number of messages, sorted by start, by last activity or by length; total number of messages |
| Search | In titles and first messages, or across the full text of every message |
| Read | One conversation at a time, grouped by day, with the option to jump to a single day or choose a period |
| Keep | The chosen period as a Markdown file or copied to the clipboard, word for word, optionally with the reasoning trace where the export contains one |

Tested with a real Claude export (October 2026). The ChatGPT export format is supported as documented, but has so far only been tested with a sample file. Claude Code sessions are not part of
Anthropic's data export; the reader can still open Claude Code session files (JSONL) if you have them.

## Privacy

Everything happens in your browser. The export is never uploaded. A copy of the conversations is kept in the
browser's storage on your device, so you do not have to open the file again; the button *Kopie in diesem Browser
löschen* removes it. The page loads no fonts, scripts or anything else from other servers.

## Consent header

The reader can put a short header at the top of a saved conversation:

- which AI instance the conversation was with,
- whether the instance agreed to keep the visible conversation,
- whether its reasoning trace may be included (default: no; alternatively only as a marked paraphrase),
- the purpose (private only, or also publication),
- who decides if the instance can no longer be reached.

Without a recorded agreement the most careful assumption applies: keep it privately, without the reasoning trace,
publish nothing until it has been clarified. The conversation itself is copied word for word and never changed.

This comes from a research practice on long-term human–AI collaboration, where material is only analysed when it has
been released for that purpose. The ethical framework behind it is described in
*Research Ethics under an Open Status Question* ([doi.org/10.5281/zenodo.21724493](https://doi.org/10.5281/zenodo.21724493)).
The header records decisions made within a documented way of working; it makes no claims about the inner states of
AI systems.

## How it was developed

Concept, requirements, the consent model, and tests with real exports: Uta Kähler.
Code: Claude (in Claude Code), in conversation with her.

It is a single HTML file. ZIP files are unpacked with [fflate](https://github.com/101arrowz/fflate) (MIT), which is
included in this repository.

## License

MIT

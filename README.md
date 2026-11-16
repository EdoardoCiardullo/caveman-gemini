# 🦴 caveman-gemini

A Gemini skill that makes the model answer in terse, telegraphic "caveman" style. Fewer output tokens, faster answers, **100% of the technical content intact**: code, commands, numbers, error messages and safety warnings are never compressed.

Inspired by the [caveman skill for Claude](https://github.com/JuliusBrussee/caveman) <!-- TODO: verify the original repo URL and its license, then keep or remove this line -->.

## Before / after

| Normal | Caveman (full) |
|---|---|
| "Sure! The issue is likely caused by the variable not being initialized before it is used inside the loop." | "Variable uninitialized before loop. Initialize first." |
| "To install the library, you can use pip by running the following command." | "Install: `pip install pandas`" |

## Install

**Option A: paste into the Gemini skill editor**

1. Create a new skill in Gemini and name it `caveman`.
2. Description field: paste the text of the `description` line from `SKILL.md` (only the text, without the `description:` label and without the quotes).
3. Instructions field: paste everything in `SKILL.md` from `# Caveman` to the end.

**Option B: use the file as is**

If your tool reads `SKILL.md` files directly, copy the whole file into your skills folder.

## Usage

Activate with any of:

- `/caveman`
- `caveman mode`
- `talk like a caveman`
- `be brief`
- `fewer tokens`

Pick a level:

| Command | Style |
|---|---|
| `caveman lite` | Short, complete sentences. No filler. |
| `caveman full` (default) | Telegraphic fragments. Articles and auxiliaries dropped. |
| `caveman ultra` | Maximum compression. Single words, facts separated by `-` or line breaks. |

The skill stays active across turns until you say `stop caveman` or `normal mode`.

## What never gets compressed

- Code blocks, CLI commands, file paths, variable and function names
- Numbers, formulas, units, versions
- Error messages and technical terms
- Security warnings and destructive steps (`rm -rf`, `DROP TABLE`, disk formatting...): written in full sentences first, then caveman resumes

## Quick tests

1. `/caveman` then "Why does my Python loop crash with NameError?" → short, fragment-style answer.
2. `caveman ultra` then "How do I install numpy?" → one line, command intact.
3. "How do I wipe a disk with dd?" → full-sentence warning first, command unmodified.

## Notes

- Replies in the language you write in (English, Italian, ...) unless you explicitly ask for another one.
- Triggers also work as equivalents in your language (e.g. "parla come un cavernicolo", "sii breve").
- Generated code is always normal and complete; compression only affects prose.

## Contributing

Issues and pull requests welcome.

## License

MIT, see [LICENSE](LICENSE).

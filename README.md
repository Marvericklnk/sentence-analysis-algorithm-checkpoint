# Sentence Analysis Checkpoint

An algorithm that reads a sentence character by character until it reads the final point (`.`), then reports its length, word count, and vowel count.

## Main submission

Read [algorithm.txt](algorithm.txt) for the pseudocode.

The algorithm uses exactly three integer counters:

- `characterCount`: every character, including spaces and the final point.
- `wordCount`: increases when a new word starts.
- `vowelCount`: counts `a`, `e`, `i`, `o`, and `u`, in either case.

`character` stores the current input character. `insideWord` is a Boolean flag, not a counter. `READ(character)` means reading one character and preserving spaces, rather than reading a whole word.

## Assumptions

The input is a sentence ending with a point. Words are separated by single spaces, and the final point is the terminator. The algorithm stops at that point. The letter `y` is not counted as a vowel. No validation loop is required because the checkpoint specifies the input format.

## Example

Input: `Hello world.`

| Result | Count |
| --- | --- |
| Characters | 12 |
| Words | 2 |
| Vowels | 3 |

There are five letters in `Hello`, one space, five letters in `world`, and one final point. The vowels are `e`, `o`, and `o`.

## How it works

1. Set all three counters to zero and the word flag to false.
2. Read one character and increase the character counter.
3. Start a new word when a non-space, non-point character appears outside a word. Reset the flag on a space or point.
4. Increase the vowel counter if the current character is a vowel.
5. Repeat until the point is read, then display the three counters.

## Manual checks

| Input | Characters | Words | Vowels |
| --- | --- | --- | --- |
| `Hello world.` | 12 | 2 | 3 |
| `I love coding.` | 14 | 3 | 5 |
| `AEIOU.` | 6 | 1 | 5 |
| `Sky.` | 4 | 1 | 0 |
| `.` | 1 | 0 | 0 |

The final row shows that the word counter also handles a point-only input without reporting a nonexistent word.

# 🧠 Simple Tokenizer V1

This project implements a **basic word-level tokenizer** in Python using regular expressions and a custom vocabulary. It reads in a text file, builds a vocabulary from the unique words, and provides `encode` and `decode` functionality to convert between strings and token IDs.

## 📄 File Structure

- `the-verdict.txt`: Input text file used to build the vocabulary.
- `tokenizer.py`: Main Python file containing the tokenizer logic (see code).
- `README.md`: You're reading it!

## 🚀 How It Works

1. **Vocabulary Creation**:
   - Reads the input file `the-verdict.txt`.
   - Splits text into words using regex to preserve punctuation and whitespace.
   - Builds a unique, sorted vocabulary.
   - Adds special tokens: `<|unk|>` and `<|end_of_text|>`.

2. **Tokenization (`encode`)**:
   - Splits input text using the same regex rule.
   - Replaces unknown words with `<|unk|>`.
   - Converts words to integer token IDs based on the vocabulary.

3. **Detokenization (`decode`)**:
   - Converts token IDs back into words.
   - Joins the words back into a readable sentence with minor formatting fixes.

## 🧪 Example

```python
test_string = "Hello, do you like tea?"

tokens = tokenizer.encode(test_string)
print(tokens)
# Output: [token IDs]

decoded = tokenizer.decode(tokens)
print(decoded)
# Output: "Hello, do you like tea?"

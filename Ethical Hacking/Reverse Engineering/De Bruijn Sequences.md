# De Bruijn Sequences

In **reverse engineering**, a **De Bruijn sequence** is a cyclic sequence used to generate all possible substrings of a certain length in a given set of characters (e.g., binary digits, alphanumeric characters).

they are used to identify offsets and pinpoint specific addresses in memory.

## Key Concepts of De Bruijn Sequences

1. **Definition**:
   - A De Bruijn sequence of order `n` over an alphabet of size `k` is a cyclic sequence in which every possible string of length `n` appears exactly once as a substring.
   - For example, a De Bruijn sequence for `n = 3` over the alphabet `{0, 1}` could be: `00010111`.

2. **Properties**:
   - Contains every possible substring of length `n`.
   - Minimal length: A De Bruijn sequence has a length of \( k^n \), where `k` is the size of the alphabet, and `n` is the substring length.

## Applications in Reverse Engineering

### 1. Buffer Overflow Exploits

- De Bruijn sequences are used to:
  - **Identify the exact location of a crash or overwrite**: During a buffer overflow attack, the sequence is input into a vulnerable program. If a crash occurs, the specific substring at the crash point helps determine the **offset** of the overwritten memory.
  - **Locate the return address or instruction pointer (EIP/RIP)**: By checking which part of the sequence is found in a register (e.g., EIP), you can calculate the offset where the program's flow is overwritten.

### 2. Fuzzing

- De Bruijn sequences help in systematically exploring memory regions, making it easier to determine how data is handled in memory.

### 3. Address Pattern Matching

- Reverse engineers can use De Bruijn sequences to uniquely map memory regions or function calls to sequence offsets.

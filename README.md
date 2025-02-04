# Parser
Context-Free Grammar (CFG)

This Python script is designed to parse sentences and extract noun phrase chunks using a **context-free grammar (CFG)**. It leverages **NLTK** (Natural Language Toolkit) for the processing and parsing of the sentence, and it prints the parse tree along with the noun phrase chunks. Here's a breakdown of the key components:

### **Grammar Definitions (TERMINALS & NONTERMINALS)**:
1. **Terminals**: These are the basic building blocks of the grammar and represent words or tokens. The terminals define the allowable words for various parts of speech (e.g., adjectives, nouns, verbs, determiners).
   - Example: `Adj -> "country" | "dreadful"`, where "country" and "dreadful" are possible adjectives.

2. **Nonterminals**: These define the syntactic categories (e.g., sentences, noun phrases) and specify how terminal symbols can be combined. They represent larger syntactic units or structures.
   - Example: `S -> SS | SS Conj SS | SS P SS` defines the structure of a sentence (`S`) as a combination of sentence (`SS`), conjunction (`Conj`), and preposition (`P`).

### **Grammar Construction**:
- **NLTK CFG (Context-Free Grammar)**: The grammar is created using `nltk.CFG.fromstring()`, which parses the `TERMINALS` and `NONTERMINALS` definitions into an NLTK grammar object that can be used for parsing sentences.

### **Parser**:
- **ChartParser**: This parser uses the CFG defined above to parse the input sentence. The parser will attempt to find a valid derivation (or parse tree) for the given sentence based on the grammar.

### **Main Function**:
1. **Input Handling**:
   - If a filename is provided as a command-line argument, the script reads the sentence from the file.
   - If no filename is provided, the user is prompted to enter a sentence manually.

2. **Preprocessing**:
   - The sentence is converted to lowercase, tokenized into words, and any non-alphabetic tokens (such as punctuation) are removed.

3. **Parsing**:
   - The `ChartParser` tries to generate a parse tree from the processed sentence. If parsing fails, an error message is displayed.

4. **Output**:
   - If parsing is successful, the program prints the resulting parse tree(s).
   - It then identifies and prints the **noun phrase chunks** (subtrees labeled as 'NP') from the parse tree.

### **Preprocessing Function (`preprocess`)**:
- **Tokenization and Cleaning**: This function tokenizes the sentence (breaks it down into individual words) and removes non-alphabetic tokens, keeping only meaningful words for further processing.

### **Noun Phrase Chunking (`np_chunk`)**:
- **Subtree Extraction**: This function searches for and extracts noun phrase chunks (subtrees labeled 'NP') from the parse tree, which are then printed as part of the output.

### **How the Program Works**:
1. **Input**: The user provides a sentence (either from a file or through direct input).
2. **Parsing**: The sentence is tokenized, and the script attempts to parse it using the specified CFG.
3. **Output**:
   - If successful, the program outputs the parse tree in a human-readable format.
   - It also extracts and prints the noun phrase chunks from the sentence, which are important components in syntactic analysis.

### **Example**:
Input sentence:  
`"The red armchair in the corner arrived with a smile."`

The script might output a parse tree for the sentence, showing how the sentence breaks down into its parts, such as subject, verb, object, etc. It will also identify noun phrase chunks, like "The red armchair" and "the corner."

### **Usage**:
To run the script, you can provide a sentence either through input or by specifying a file with the sentence. For example:
```bash
python parse_noun_phrases.py "The little red armchair in the corner arrived."
```
or, if using a file:
```bash
python parse_noun_phrases.py sentence.txt
```

### **Key Points**:
- **NLTK**: Used for natural language processing tasks, such as tokenization and parsing.
- **CFG**: A context-free grammar is used to define sentence structure rules.
- **Chunking**: The script extracts noun phrase chunks from the parse tree, which can be useful for further syntactic or semantic analysis.

NOTE:USE YOUR OWN SENTENSES, CANNOT DISCLOSE MY DATA DUE TO CONFIDENTIALITY.

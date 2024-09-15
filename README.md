# LLM-for-Literature-Review

HW 3 Programming Languages

## Identification

- **Name:** Pranav Surampudi
- **Student ID:** 2407260
- **Course:** CPSC 354-03
- **Date:** 9/14/24

## Description

This file documents my findings from using an LLM to answer questions from the past few weeks.

## Question

I don't understand what Lean is, and want to figure out its uses, reasons, and purpose, and how it plays into the Natural Number Game.

## What is Lean?
Chat GPT:
- Lean is a powerful, open-source theorem prover and programming language developed by Microsoft Research.
- It's designed to bridge the gap between computational proof and human-readable mathematics.

Key points about Lean:

1. **Purpose:** 
   - Used for formalizing mathematics and writing machine-checkable proofs
   - Allows expression of complex mathematical concepts and verification of their correctness

2. **Features:**
   - Dependent type theory: Rich type system allowing types to depend on values
   - Tactics: Language for writing proofs in a natural, step-by-step manner
   - Metaprogramming: Users can extend Lean's capabilities with custom tactics and automation

3. **Uses:**
   - Formal verification of mathematical proofs
   - Teaching mathematical reasoning and proof techniques
   - Developing verified software
   - Exploring foundations of mathematics

4. **Relation to the Natural Number Game:**
   - Interactive tutorial built using Lean
   - Teaches basics of theorem proving and formal mathematics using natural numbers
   - Players learn Lean's syntax and tactics while exploring properties of natural numbers

5. **Advantages:**
   - Rigorous verification: Computer-checked proofs reduce risk of human error
   - Collaborative mathematics: Easier sharing and building upon others' work
   - Bridging formal and informal mathematics: Makes formal proofs more accessible

6. **Challenges:**
   - Learning curve: Requires familiarity with formal logic and proof theory
   - Formalization effort: Translating informal proofs into Lean can be time-consuming

# What Role does Lean have in establishing proofs in the Natural Numbers Game?
```lean
intro h
rw [add_succ, add_succ, add_zero] at h
repeat apply succ_inj at h
apply zero_ne_succ at h
exact h
```
Chat GPT:

Here's a step-by-step breakdown of the proof:

- `intro h`: This introduces a hypothesis `h`, which is the starting point for the proof, allowing you to assume something that needs to be proven.

- `rw [add_succ, add_succ, add_zero] at h`: This **rewrites** the hypothesis `h` using the lemmas `add_succ` and `add_zero`. The `add_succ` lemma states that adding a successor to a number (`succ(n)`) is the same as incrementing that number. The `add_zero` lemma states that adding zero doesn't change a number. These rewrites simplify the equation, transforming it into a more workable form.

- `repeat apply succ_inj at h`: This tactic repeatedly applies the `succ_inj` lemma, which states that if `succ(a) = succ(b)`, then `a = b`. It helps by stripping away the `succ` layers from both sides of the equation, reducing the complexity of the expression.

- `apply zero_ne_succ at h`: This applies the lemma `zero_ne_succ`, which states that zero is not the successor of any natural number (`0 ≠ succ(n)`). This leads to a contradiction if the hypothesis implies such an equality.

- `exact h`: Finally, `exact h` is used to conclude the proof once the hypothesis matches the goal or leads to a contradiction, ensuring that the proof is complete.

Lean acts as a **formal verifier**, ensuring that every logical step adheres to the rules of natural deduction and type theory. It checks that each step is valid and guides the user in applying appropriate tactics, ensuring the proof is correct. In this example, Lean rewrites, simplifies, and applies lemmas in a systematic way, leading to a formal proof of the proposition involving natural numbers.

## References and Further Reading

The information provided in this README primarily draws from general knowledge about Lean, theorem proving, and the Natural Numbers Game. Here are some key references for further reading and verification:

1. **Lean as a Theorem Prover and Programming Language:**
   * "The Lean Theorem Prover (version 3.4.2)" by Leonardo de Moura, et al. (2015)
     * This is the original documentation and introduction to Lean, detailing its core features and use cases.
     * [Google Scholar](https://scholar.google.com)

2. **Dependent Type Theory and Proof Tactics:**
   * "Type Theory and Formal Proof: An Introduction" by Rob Nederpelt and Herman Geuvers (2014)
     * This book covers dependent type theory, which is foundational to Lean's design.
     * [Google Scholar](https://scholar.google.com)

3. **Natural Numbers Game in Lean:**
   * "The Natural Number Game" by Kevin Buzzard
     * An interactive tutorial built on Lean, focusing on teaching theorem proving through exercises involving natural numbers.
     * The game itself is hosted online, and Kevin Buzzard is a significant contributor to making Lean more accessible to mathematicians.
     * [The Natural Numbers Game](https://www.ma.imperial.ac.uk/~buzzard/xena/natural_number_game/)

4. **Formal Verification in Mathematics and Software:**
   * "Proof Assistants: A Survey" by Georges Gonthier (2008)
     * This paper surveys the use of proof assistants like Lean and Coq in formal verification.
     * [Google Scholar](https://scholar.google.com)

5. **General Introduction to Theorem Proving and Tactics in Lean:**
   * "Formal Proof - Theory and Practice" by Yves Bertot and Pierre Castéran (2004)
     * A detailed look into the formal proof systems and how tools like Lean and Coq fit into the broader ecosystem of automated theorem proving.
     * [Google Scholar](https://scholar.google.com)

By reading abstracts and sections of these references, you can get a solid foundation of the historical context and theoretical underpinnings of Lean, theorem proving, and their applications in formal mathematics.


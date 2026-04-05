# Rule: Lesson Content

## Scope

This rule applies to all lesson and lecture files in the course:
- `**/*lesson*.md`
- `**/modules/**/*.md`
- `**/Section-*/**/*.md`

## Core Structure

Every lesson must contain these three elements:

### 1. Learning Objective (Required)

At the beginning of the lesson, clearly state what students will be able to do or understand:

```markdown
**Learning Objective:** By the end of this lesson, you will be able to [action verb] [concept/skill].
```

Examples:
- "By the end of this lesson, you will be able to implement a basic Claude API call in Python."
- "By the end of this lesson, you will understand the difference between prompt engineering and fine-tuning."

The objective should be:
- Action-oriented (use verbs like: understand, implement, apply, analyze, create)
- Measurable (testable by an exercise or quiz)
- Achievable within the lesson time estimate

### 2. Main Content (Required)

Organized with clear section hierarchy:

**Heading Levels:**
- `#` → Lesson title (one per file, at top)
- `##` → Major sections (core concepts, main ideas)
- `###` → Subsections (details, breakdowns, related ideas)
- `####` → Detail paragraphs (rarely used, keep to 2-3 levels max)

**Content Rules:**
- Use plain language first, technical terms second (see "First Explain, Then Name" rule below)
- One idea per paragraph
- Break long explanations into 2-3 shorter paragraphs
- Use bullet points for lists (unordered) and numbered lists for sequences
- Bold key terms and concepts on first mention

**Code Examples (Mandatory):**

Every technical concept must include at least one code example or scenario.

Format:
````markdown
```python
# Example: [brief description]
[executable code]
```
````

Rules for code blocks:
- Specify language (python, javascript, yaml, bash, etc.)
- Include a comment describing what the code does
- Code must be correct and runnable (test before including)
- If code is hypothetical or pseudocode, mark it: `python (pseudocode)`

**Example Requirement:**
- Every lesson must have at least 1-2 concrete examples
- Examples should show the concept in action
- For transcript-based lessons: preserve examples from the lecture

### 3. Summary (Required)

At the end of every lesson, include:

```markdown
## Summary

[One-sentence recap of the main idea]

**Key Takeaway:** [One sentence about why this matters or how you'll use it]

**Next Lesson:** [Brief preview of what comes next, or link to next lesson]
```

The summary should:
- Recap what was taught (not what should have been taught)
- Highlight the practical application
- Create a bridge to the next topic
- Be readable in 30 seconds

## First Explain, Then Name

**Core Principle:** Introduce concepts by explaining what they do, then give them the technical name.

### Anti-Pattern
```
"A module is a collection of functions satisfying the CommonJS spec..."
```

### Correct Pattern
```
"When you want to organize code into reusable pieces that don't pollute the global namespace, you group them in a file. Other files can then use only the pieces they need from that file. This pattern is called a module."
```

**Application:**
- When introducing ANY new term (framework, algorithm, pattern, tool):
  1. Explain the problem it solves or the idea behind it
  2. Show a simple example or analogy
  3. Then give the technical term
  4. Explain what the term means in light of what you just showed

**Example:**
```markdown
## Inheritance

Sometimes you have several classes that do very similar things, with only small differences. Instead of copying the same code into each class, you can create a base class with the shared code, and have the other classes extend it to add their own special behavior. This pattern is called inheritance.

```python
# Example: Inheritance
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        print(f"{self.name} makes a sound")

class Dog(Animal):
    def speak(self):
        print(f"{self.name} barks")
```
```

## Transcript-Based Lessons

If this lesson is adapted from a lecture transcript:

- **Preserve the author's voice** — don't rewrite into formal article style
- **Keep the lecture flow** — maintain the order and logical progression of the original lecture
- **Preserve examples** — the lecturer's examples are authentic and valuable
- **Clean up mechanics only** — remove filler words, fix grammar, add paragraph breaks, but don't rephrase
- **Add structure** — break transcript into sections with markdown headings, add learning objective and summary

**Special instruction:** When converting transcript to lesson format, ask: "Is this rewritten or preserved?" If you've substantially rewritten, you've gone too far.

## Length Guidelines

- **Minimum:** 300 words (substantial content)
- **Typical:** 800-1500 words (good teaching depth)
- **Maximum:** 2500 words (split into 2 lessons if longer)

Too short: feels incomplete, doesn't allow for proper explanation and examples.
Too long: overwhelming, should be broken into separate focused lessons.

## Quality Checklist

For every lesson file, verify:

- [ ] Learning objective stated clearly at top
- [ ] Main content organized with ## and ### headings
- [ ] At least one code example or concrete scenario
- [ ] All technical terms explained at first mention
- [ ] Examples are correct and runnable
- [ ] Summary section at bottom with key takeaway
- [ ] Author's voice preserved (if transcript-based)
- [ ] Length between 300-2500 words
- [ ] No unexplained jargon
- [ ] Binary understanding test: After reading, could a student answer "what's next?"

## Binary Understanding Test

After reading each lesson section, a student should be able to answer: **"What will I do with this knowledge?"** or **"What problem does this solve?"**

If the answer is unclear, the explanation needs clarification. Rewrite for clarity.

## Related Rules

- See `course-structure.md` for how lessons fit into modules and courses
- See `exercises-quizzes.md` for practice materials that follow this lesson

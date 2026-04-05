# Rule: Exercises & Quizzes

## Scope

This rule applies to all practice and assessment materials:
- `**/exercise*.md` (practical exercises)
- `**/quiz*.yaml` (quiz configurations)
- `**/quiz*.md` (quiz instructions)
- `**/homework*.md` (homework assignments)

## Exercise Design (Markdown Format)

Every exercise must be a solvable, standalone practice activity that reinforces one or more lessons.

### Required Fields

```markdown
# Exercise: [Exercise Name]

**Module:** [Module number/name]
**Related Lessons:** [Lesson 1](../Section-XX/lesson-XX.md), [Lesson 2](../Section-XX/lesson-XX.md)
**Goal:** [What will you build or accomplish?]
**Time Estimate:** [15-60 minutes]
**Difficulty:** [Beginner / Intermediate / Advanced]

## Problem Statement

[What problem are you solving? What is the real-world context?]

[Paragraph 2 if needed]

## Instructions

[Step-by-step walkthrough that students can follow]

### Step 1: [First step]

[Details and any code starter templates]

### Step 2: [Second step]

[Continue with detail]

### Step 3: [Continue]

[Final step]

## Expected Result

[What does success look like? Describe the output or outcome.]

Example output:
```
[Show what a complete solution looks like]
```

## Hints

[Optional: If students are stuck, provide progressive hints]

### Hint 1 (Start here)
[First nudge in the right direction]

### Hint 2 (Still stuck?)
[More specific guidance]

### Hint 3 (Last resort)
[Near-complete example or solution approach]

## Advanced Challenge (Optional)

[For advanced students: what's the next step beyond the basic exercise?]

## Resources

- [Related documentation](URL)
- [Code template](../code/template.py)
```

### Exercise Quality Rules

**Solvability:**
- Must be completable by a student who has done all prerequisite lessons
- Takes the stated time (test this by timing yourself)
- Has one clear correct answer or set of correct answers
- Provides enough guidance that students aren't stuck (use hints)

**Relevance:**
- Directly applies concepts from linked lessons
- Teaches a practical skill students will use
- Has a real-world context or purpose (not artificial)

**Progression:**
- Within a module: exercises build in difficulty (easy → medium → hard)
- First exercise in a module should be straightforward
- Exercises can combine concepts from earlier lessons

**Scaffold:**
- First exercise: more detailed instructions, more guidance
- Later exercises: less detailed instructions, more independence
- Final capstone exercise: integrate multiple modules

### Example Exercise

```markdown
# Exercise: Build Your First Claude API Call

**Module:** 1 — Getting Started
**Related Lessons:** [Lesson 1: Claude Setup](../Section-01/lesson-01.md), [Lesson 2: API Keys](../Section-01/lesson-02.md)
**Goal:** Make a successful API call to Claude and capture the response
**Time Estimate:** 20 minutes
**Difficulty:** Beginner

## Problem Statement

You have a Claude API key. Now you'll use it to make your first request to the Claude API. This is the foundation for all Claude integrations — learning to make this call correctly is essential.

## Instructions

### Step 1: Set up your Python environment

Create a new file called `hello_claude.py`. At the top, import the required library:

```python
from anthropic import Anthropic

client = Anthropic(api_key="your-api-key-here")
```

Replace `"your-api-key-here"` with your actual API key from the dashboard.

### Step 2: Make your first API call

Add this code:

```python
message = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    max_tokens=100,
    messages=[
        {"role": "user", "content": "Say hello and tell me your name"}
    ]
)

print(message.content[0].text)
```

### Step 3: Run the script

From your terminal:

```bash
python hello_claude.py
```

## Expected Result

You should see output like:

```
Hello! I'm Claude, an AI assistant made by Anthropic. I'm here to help with a wide variety of tasks, from answering questions and helping with analysis to brainstorming ideas and explaining complex topics. How can I help you today?
```

(The exact response will vary — Claude provides different responses each time.)

## Hints

### Hint 1 (Start here)
Make sure your API key is correctly set in your environment. You can test this by printing it: `print(os.environ.get('ANTHROPIC_API_KEY'))`

### Hint 2 (Still stuck?)
If you get an authentication error, double-check that you've copied your API key exactly as shown in the dashboard. API keys are case-sensitive.

### Hint 3 (Last resort)
Here's a complete working example:
```python
import os
from anthropic import Anthropic

client = Anthropic(api_key=os.environ.get("ANTHROPIC_API_KEY"))
message = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    max_tokens=100,
    messages=[{"role": "user", "content": "Say hello"}]
)
print(message.content[0].text)
```

## Advanced Challenge

Modify the code to:
1. Ask Claude a question about a topic you're interested in
2. Capture Claude's response
3. Use Claude's response in a follow-up question (building a conversation)
```

## Quiz Design (YAML Format)

Quizzes test comprehension of lessons. Use YAML format for structured data:

### Format

```yaml
# quiz-module-01.yaml
title: "Module 1: Fundamentals — Knowledge Check"
module: 1
description: "Test your understanding of core concepts from Module 1"

questions:
  - id: q1
    type: "multiple_choice"
    question: "What is [concept]?"
    options:
      - "Incorrect answer A"
      - "Correct answer (this should be marked as correct)"
      - "Incorrect answer B"
    correct_answer: 1  # Index of correct option (0-based)
    explanation: "This is correct because [reason]. [Related lesson](../Section-01/lesson-01.md)"

  - id: q2
    type: "true_false"
    question: "Is [statement] true or false?"
    correct_answer: true
    explanation: "This is true because [reason]."

  - id: q3
    type: "multiple_select"
    question: "Which of these are [category]? (Select all that apply)"
    options:
      - "Option A (correct)"
      - "Option B (incorrect)"
      - "Option C (correct)"
      - "Option D (incorrect)"
    correct_answers: [0, 2]  # Indices of correct options
    explanation: "Options A and C are correct because..."

  - id: q4
    type: "short_answer"
    question: "Explain [concept] in your own words."
    sample_answer: "A good answer would explain [key points]"
    explanation: "Look for answers that include: [point 1], [point 2], [point 3]"
```

### Question Types

**Multiple Choice:**
- One correct answer
- 3-4 options typical
- Mark correct answer by index (0-based)

**True/False:**
- Binary choice
- Use for testing factual knowledge
- Always include explanation of why answer is correct

**Multiple Select:**
- 2+ correct answers
- 4-5 options typical
- Students must select all correct answers to get full credit

**Short Answer:**
- Free-form text response
- Provide sample good answer
- Mention what key concepts to look for in responses

### Quiz Quality Rules

**Coverage:**
- One quiz per module (or per 3-4 lessons)
- Questions cover all major concepts
- Questions test different levels: remember, understand, apply

**Difficulty Progression:**
- First 2-3 questions: recall basic facts
- Middle questions: apply concepts
- Last question (optional): integrate multiple concepts

**Clarity:**
- Question text is clear and unambiguous
- Distractors are plausible but clearly wrong
- Correct answer is definitely correct
- Explanations teach, not just confirm/deny

**Fairness:**
- All information needed to answer comes from lessons
- No trick questions
- No unfairly difficult vocabulary

### Example Quiz

```yaml
title: "Module 1: Claude Fundamentals — Check Your Knowledge"
module: 1
passing_score: 70

questions:
  - id: q1
    type: "multiple_choice"
    question: "What is the primary purpose of a system prompt in Claude?"
    options:
      - "To prevent Claude from making mistakes"
      - "To set the context and define how Claude should behave and respond"
      - "To limit the length of Claude's responses"
      - "To automatically correct user input"
    correct_answer: 1
    explanation: "The system prompt sets the context, defines Claude's role, and guides how it should approach tasks. It's the foundation for shaping Claude's behavior. [See System Prompts](../Section-01/lesson-02.md)"

  - id: q2
    type: "true_false"
    question: "Claude always provides the same response to the same prompt."
    correct_answer: false
    explanation: "Claude uses temperature sampling, which means it generates different responses to the same prompt. This is by design — it allows for creativity and variety. [See Temperature & Sampling](../Section-01/lesson-03.md)"

  - id: q3
    type: "multiple_select"
    question: "Which of these are valid use cases for Claude's API? (Select all that apply)"
    options:
      - "Building a customer support chatbot"
      - "Analyzing and summarizing documents"
      - "Replacing all human decision-making"
      - "Generating creative content like blog posts"
    correct_answers: [0, 1, 3]
    explanation: "Options 1, 2, and 4 are valid. Claude works well for customer support, analysis, and content generation. However, Claude should augment (not replace) human judgment in critical decisions. [See Use Cases](../Section-02/lesson-05.md)"

  - id: q4
    type: "short_answer"
    question: "Describe what 'token counting' means and why it matters in the Claude API."
    sample_answer: "Tokens are the chunks of text that Claude reads and generates. Each API call is charged by tokens used. Token counting matters because it helps you estimate costs and avoid exceeding token limits."
    explanation: "A good answer explains that tokens are text units and mentions either cost estimation or token limits. See [Tokens & Counting](../Section-01/lesson-04.md) for full details."
```

## Placement Within Courses

**Exercise placement:**
- After the lesson(s) that teach the required concepts
- Early exercises (module 1-2): individual simple skills
- Later exercises (module 3+): combine multiple concepts
- Final exercise: capstone project integrating the entire course

**Quiz placement:**
- After each module (not after every lesson)
- Before moving to the next module
- Optional: include one question per lesson in module quiz

## Difficulty Progression

Within a module, structure exercises by difficulty:

**Beginner exercise:**
- Heavily scaffolded (step-by-step instructions)
- Code templates provided
- ~15-30 minutes
- Tests single concept

**Intermediate exercise:**
- Moderate scaffolding
- Less complete code templates
- ~30-60 minutes
- Combines 2-3 concepts

**Advanced exercise:**
- Minimal scaffolding
- No code templates
- ~60+ minutes
- Integrates all module concepts
- Open-ended (multiple valid solutions)

## Prerequisites for Exercises

Every exercise must have:
- All prerequisite knowledge from related lessons
- Clear learning outcomes from those lessons
- No dependencies on future lessons

**Anti-pattern:** Exercise that requires knowledge from Module 3 when it appears in Module 1.

## Quality Checklist

- [ ] Exercise has clear goal and real-world context
- [ ] Time estimate tested and accurate
- [ ] Instructions are step-by-step and followable
- [ ] Expected result clearly defined
- [ ] Difficulty level appropriate for module
- [ ] Solvable with only prerequisite lesson knowledge
- [ ] Hints provided (progressive from general to specific)
- [ ] Quiz tests all major module concepts
- [ ] Quiz passes/difficulty appropriate (60-80% for passing)
- [ ] Questions clearly stated, unambiguous
- [ ] Correct answers are definitely correct
- [ ] Explanations educate and reference related lessons
- [ ] Exercises progress from simple to complex

## Related Rules

- See `lesson-content.md` for the lessons that precede these exercises
- See `course-structure.md` for where exercises fit in the module hierarchy

# Advanced Prompt Engineering Techniques

## Table of Contents
1. Chain-of-Thought Prompting
2. Few-Shot Learning
3. Structured Output with XML
4. Role-Based Prompting
5. Prefilling Responses
6. Prompt Chaining
7. Context Management
8. Multimodal Prompting

## 1. Chain-of-Thought (CoT) Prompting

### What It Is
Encouraging Claude to break down complex reasoning into explicit steps before providing a final answer.

### When to Use
- Complex reasoning tasks
- Multi-step problems
- Tasks requiring justification
- When consistency matters

### Basic Structure
```
Let's think through this step by step:

Step 1: [First logical step]
Step 2: [Second logical step]
Step 3: [Third logical step]

Therefore: [Conclusion]
```

### Example
```
Problem: A store sells apples for $2 each and oranges for $3 each. 
If I buy 5 apples and 3 oranges, how much do I spend?

Let's think through this step by step:

Step 1: Calculate apple cost
- 5 apples × $2 per apple = $10

Step 2: Calculate orange cost
- 3 oranges × $3 per orange = $9

Step 3: Calculate total
- $10 + $9 = $19

Therefore: You spend $19 total.
```

## 2. Few-Shot Learning

### What It Is
Providing examples to guide Claude's behavior without explicit instructions.

### Types

#### 1-Shot (Single Example)
Best for: Simple, straightforward tasks
```
Example: "Happy" → Positive
Now classify: "Terrible" →
```

#### 2-Shot (Two Examples)
Best for: Moderate complexity
```
Example 1: "Great product!" → Positive
Example 2: "Doesn't work well" → Negative
Now classify: "It's okay" →
```

#### Multi-Shot (Multiple Examples)
Best for: Complex patterns, edge cases
```
Example 1: "Love it!" → Positive
Example 2: "Hate it" → Negative
Example 3: "It's fine" → Neutral
Example 4: "Could be better" → Neutral
Example 5: "Amazing!" → Positive
Now classify: "Not bad" →
```

## 3. Structured Output with XML Tags

### What It Is
Using XML tags to structure prompts and guide output format.

### Benefits
- Clear structure
- Easy parsing
- Reduced ambiguity
- Better organization

### Common Patterns

#### Task Definition
```xml
<task>
  <objective>What to accomplish</objective>
  <constraints>Limitations and rules</constraints>
  <format>Expected output format</format>
</task>
```

## 4. Role-Based Prompting

### What It Is
Assigning Claude a specific role or expertise to guide behavior.

### Structure
```
You are a [ROLE] with expertise in [DOMAIN].

Your responsibilities:
- [Responsibility 1]
- [Responsibility 2]
- [Responsibility 3]

Your task: [Specific task]
```

## 5. Prefilling Responses

### What It Is
Starting Claude's response to guide format and tone.

### Benefits
- Ensures correct format
- Sets tone and style
- Guides reasoning
- Improves consistency

## 6. Prompt Chaining

### What It Is
Breaking complex tasks into sequential prompts, using outputs as inputs.

### Structure
```
Prompt 1: Analyze/Extract
↓
Output 1: Structured data
↓
Prompt 2: Process/Transform
↓
Output 2: Processed data
↓
Prompt 3: Generate/Synthesize
↓
Final Output: Result
```

## 7. Context Management

### What It Is
Strategically managing information to optimize token usage and clarity.

### Techniques

#### Progressive Disclosure
```
Start with: High-level overview
Then provide: Relevant details
Finally include: Edge cases and exceptions
```

#### Hierarchical Organization
```
Level 1: Core concept
├── Level 2: Key components
│   ├── Level 3: Specific details
│   └── Level 3: Implementation notes
└── Level 2: Related concepts
```

## 8. Multimodal Prompting

### Vision Prompting

#### Structure
```
Analyze this image:
[IMAGE]

Specifically, identify:
1. [What to look for]
2. [What to analyze]
3. [What to extract]

Format your response as:
[Desired format]
```

### File-Based Prompting

#### Structure
```
Analyze this document:
[FILE]

Extract:
- [Information type 1]
- [Information type 2]
- [Information type 3]

Format as:
[Desired format]
```

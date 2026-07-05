
# engram

### An AI-Powered Study System That Knows What You're About to Forget

---

## The Problem

Students waste enormous amounts of time studying things they already know
while neglecting what they are actually about to forget. When you open your
notes before an exam, you have no reliable way to know which topics are solid
in your memory and which ones are slipping away.

So you either study everything equally — which is wasteful — or you study
whatever "feels" hard — which is unreliable.

Existing tools do not solve this:

- **Flashcard apps** treat every card as isolated and use the same fixed
  review intervals for every person on earth.
- **AI tutors from the cloud** hallucinate, cost money, and have no idea
  what YOU personally remember.
- **Generic study apps** show dashboards but give no actionable intelligence.

There is no tool that combines understanding of the content, understanding
of how concepts depend on each other, and understanding of what this
specific student is about to forget — all in one place.

engram is that tool.

---

## What engram Does

engram sits on the student's device. The student feeds it their actual
study materials — lecture notes, textbook PDFs, slides, anything.

The system does not just store these materials. It:

1. **Understands the content** — breaks materials into concepts and maps
   how they relate to each other.
2. **Models the student's memory** — predicts which concepts are about to
   fade based on how this specific student learns and forgets.
3. **Generates targeted quizzes** — tests the student on exactly what they
   are weakest on, using questions built from their own materials.
4. **Predicts exam readiness** — tells the student how prepared they are
   and gives a prioritized study plan before the exam.

The student does not need to organize anything. They do not need to make
flashcards. They drop in their materials, pick a chapter, and start
studying within seconds.

---

## How It Works — The Full Journey

### Stage 1: Upload

The student drops their materials into the app. A PDF, a set of lecture
notes, slides, or pasted text.

The system does NOT process the entire document immediately. Instead, it
performs a quick structural scan — reads the table of contents, identifies
chapter boundaries, headings, and sections — and presents the student with
a map of their materials.

A 400-page textbook is scanned in 10-15 seconds. The student sees:

    "Your book has 56 chapters. Which one do you want to study?"

The student is never blocked. They are never asked to wait. They pick a
chapter and start within seconds.

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│   Student drops PDF into the app                         │
│                                                          │
│                    │                                     │
│                    ▼                                     │
│   ┌──────────────────────────────────┐                   │
│   │     QUICK STRUCTURAL SCAN        │                   │
│   │                                  │                   │
│   │   Reads table of contents        │                   │
│   │   Identifies chapter boundaries  │                   │
│   │   Maps page numbers to chapters  │                   │
│   │                                  │                   │
│   │   Time: 10-15 seconds            │                   │
│   └────────────────┬─────────────────┘                   │
│                    │                                     │
│                    ▼                                     │
│   ┌──────────────────────────────────┐                   │
│   │     STUDENT SEES CHAPTER LIST    │                   │
│   │                                  │                   │
│   │   Chapter 1: The Chemistry       │                   │
│   │     of Life                      │                   │
│   │   Chapter 2: Chemical Context    │                   │
│   │     of Life                      │                   │
│   │   ...                            │                   │
│   │   Chapter 12: The Cell Cycle     │  ◄── Student      │
│   │   ...                            │       picks this  │
│   │   Chapter 56: Ecology            │                   │
│   │                                  │                   │
│   └──────────────────────────────────┘                   │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Stage 2: Chapter Processing

When the student picks a chapter, the system processes ONLY that chapter.
Not the whole book. Just the 25-30 pages the student needs right now.

Processing means three things happen:

**First — Text Extraction and Chunking**

The chapter's text is read and split into small meaningful pieces. Each
piece is roughly one self-contained idea — a definition, an explanation,
an example, a process description. The system respects natural boundaries
like paragraphs and sections rather than cutting text arbitrarily.

A typical chapter becomes 150-250 chunks.

**Second — Concept Identification**

The system scans the chunks to find key concepts. It identifies them
through multiple signals:

- Words in bold or italics
- Terms in headings and subheadings
- Sentences that follow definition patterns ("X is defined as...",
  "X refers to...", "The process of X occurs when...")
- Terms that appear in the chapter's review questions
- Words that are repeated frequently with explanatory context

A typical chapter yields 30-60 key concepts.

**Third — Relationship Mapping**

The system figures out how concepts in this chapter relate to each other.
It does this by looking at:

- Which concepts appear together in the same chunk
- Explicit references ("as discussed in the previous section...")
- Contrast language ("unlike X, Y does not require...")
- Dependency signals ("to understand X, one must first know Y")
- Cause and effect language ("X leads to Y", "X is caused by Y")

This creates a local knowledge map for the chapter.

**The entire processing of one chapter takes 5-10 seconds.**

While it happens, the student is already seeing the list of topics in the
chapter and can choose which area to focus on. By the time they make their
selection, processing is complete.

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│   Student picks Chapter 12: The Cell Cycle               │
│                                                          │
│                    │                                     │
│                    ▼                                     │
│   ┌──────────────────────────────────┐                   │
│   │     PROCESS THIS CHAPTER ONLY    │                   │
│   │                                  │                   │
│   │   Extract text (25-30 pages)     │                   │
│   │   Split into chunks (150-250)    │                   │
│   │   Identify concepts (30-60)      │                   │
│   │   Map relationships              │                   │
│   │                                  │                   │
│   │   Time: 5-10 seconds             │                   │
│   └────────────────┬─────────────────┘                   │
│                    │                                     │
│                    ▼                                     │
│   ┌──────────────────────────────────┐                   │
│   │     CHAPTER IS READY             │                   │
│   │                                  │                   │
│   │   47 key concepts identified     │                   │
│   │   12 concept relationships found │                   │
│   │   4 concept clusters detected    │                   │
│   │                                  │                   │
│   │   "Ready to start studying."     │                   │
│   └──────────────────────────────────┘                   │
│                                                          │
│   Total time from upload to studying: 30-40 seconds      │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Stage 3: Studying Through Quizzes

The student does not just read their notes through the tool. The tool
tests them. This is where the real learning happens.

**How questions are generated:**

The system takes a concept and retrieves the chunks from the student's
materials that are most relevant to that concept. It then creates
questions that test understanding at different levels:

- **Recall level:** "According to your notes, what is the function of
  the centrosome during cell division?"
- **Understanding level:** "Your notes describe both mitosis and meiosis.
  Explain how the outcomes differ."
- **Application level:** "If a cell skipped the G1 checkpoint, what
  problems could arise based on what your notes describe?"

Every question is built from the student's actual materials. The system
does not pull from general knowledge. It works only with what the student
gave it.

**How answers are evaluated:**

When the student answers, the system compares their response against the
source chunks. It checks:

- Did the student include the key facts that are in the source?
- Did they get the relationships between concepts right?
- What did they miss that the source material covers?
- What did they include that is NOT in the source? (noted but not
  counted as wrong — it might be correct, but the system cannot
  verify it from the materials provided)

The student receives specific feedback: "You correctly identified the
function of the centrosome. You missed that your notes also describe
its role in forming the mitotic spindle — see page 294, paragraph 2."

**How the system decides what to ask next:**

This is not random. After each answer, the system updates its model
of the student's knowledge and selects the next question based on:

1. What the student just got wrong (immediate reinforcement)
2. What concept is most at risk of being forgotten (memory decay)
3. What concept is a prerequisite for other weak concepts
   (foundational priority)
4. What the student has not been tested on yet (coverage)

The order is never the same twice. It adapts in real time to the
student's performance.

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                    THE QUIZ CYCLE                        │
│                                                          │
│   ┌──────────┐     ┌──────────┐     ┌──────────┐       │
│   │          │     │          │     │          │       │
│   │  SELECT  │────▶│ GENERATE │────▶│ STUDENT  │       │
│   │  CONCEPT │     │ QUESTION │     │ ANSWERS  │       │
│   │          │     │          │     │          │       │
│   └──────────┘     └──────────┘     └────┬─────┘       │
│        ▲                                  │             │
│        │                                  ▼             │
│        │          ┌──────────┐     ┌──────────┐        │
│        │          │          │     │          │        │
│        └──────────│  UPDATE  │◀────│ EVALUATE │        │
│                   │ MEMORY   │     │  ANSWER  │        │
│                   │  MODEL   │     │          │        │
│                   │          │     │          │        │
│                   └──────────┘     └──────────┘        │
│                                                          │
│   This cycle repeats continuously during study session.  │
│   Each cycle takes 30-60 seconds including student       │
│   thinking time.                                         │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

---

## The Three Systems That Make It Work

engram is not one algorithm. It is three systems working together.
Each one is useless without the other two.

### System 1: The Knowledge Map

**What it is:**

A graph of every concept in the student's materials, connected by the
relationships between them. Think of it as a map where each city is a
concept and each road is a relationship.

```
                     ┌───────────────┐
                     │    Cell       │
                     │   Division    │
                     └───────┬───────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
              ▼              ▼              ▼
     ┌──────────────┐ ┌────────────┐ ┌──────────────┐
     │   Mitosis    │ │  Meiosis   │ │   Cell       │
     │              │ │            │ │   Cycle      │
     │              │ │            │ │   Checkpoints│
     └──────┬───────┘ └─────┬──────┘ └──────┬───────┘
            │               │               │
     ┌──────┴──────┐        │        ┌──────┴──────┐
     │             │        │        │             │
     ▼             ▼        ▼        ▼             ▼
┌─────────┐ ┌─────────┐ ┌──────┐ ┌───────┐ ┌──────────┐
│Mitotic  │ │Cytokine-│ │Gamete│ │G1     │ │Tumor     │
│Spindle  │ │sis      │ │Forma-│ │Check- │ │Suppressor│
│Formation│ │         │ │tion  │ │point  │ │Genes     │
└─────────┘ └─────────┘ └──────┘ └───────┘ └──────────┘
```

**Why it matters:**

Without this map, the system treats every concept as independent. With
this map, the system understands that if a student forgets "mitosis,"
then "mitotic spindle formation" and "cytokinesis" are also at risk —
even if the student reviewed those topics recently.

This means the system can prioritize intelligently. It does not just
ask "what is the student about to forget?" It asks "what is the student
about to forget that will cause the most damage to everything else?"

**How it builds over time:**

The knowledge map starts with one chapter. As the student studies more
chapters, the maps connect. Concepts from Chapter 7 that are
prerequisites for Chapter 12 get linked across chapters.

Eventually the student has a complete map of the entire subject — not
because the system processed everything at once, but because the map
grew organically as the student studied.

The student can see this map. They can zoom in on a chapter or zoom
out to see the whole subject. They can see which concepts they know
well (highlighted green) and which are weak (highlighted red). This
alone is valuable — most students have never seen the structure of
what they are studying laid out visually.

---

### System 2: The Forgetting Model

**What it is:**

A mathematical model that predicts how strong the student's memory of
each concept is RIGHT NOW, and how it will change over the coming days.

Every concept the student has been tested on has a memory strength —
a number between 0 and 100 that represents how likely the student is
to recall it successfully.

```
MEMORY STRENGTH OVER TIME

100│ ●
   │  ╲
 80│   ╲         ●
   │    ╲       ╱ ╲
 60│     ╲     ╱   ╲         ●
   │      ╲   ╱     ╲       ╱ ╲
 40│       ╲ ╱       ╲     ╱   ╲
   │        ●         ╲   ╱     ╲
 20│                    ╲ ╱       ╲
   │                     ●         ╲
  0│─────────────────────────────────●──────
   Day1  Day3  Day5  Day7  Day9  Day11  Day13

   ● = review happened (strength jumps back up)
   ╲ = forgetting (strength decays over time)

   Notice: each review makes the decay SLOWER.
   The student retains longer each time.
```

**How it personalizes:**

The model does not use generic forgetting curves. It learns THIS
student's patterns.

When the student answers a question about a concept, the system
compares the prediction against reality.

```
PREDICTION: Student has 60% memory strength on "mitosis."
            Model expects a 60% chance they get it right.

REALITY:   Student got it right.

ACTION:    The model was accurate. Slightly increase confidence
           in the model's predictions for this type of concept.

---

PREDICTION: Student has 75% memory strength on "DNA replication."
            Model expects a 75% chance they get it right.

REALITY:   Student got it wrong.

ACTION:    The model overestimated. Adjust — this student forgets
           molecular biology concepts faster than the model predicted.
           Future predictions for similar concepts decay faster.
```

Over many quiz cycles, the model builds a picture of how THIS specific
student's memory works across different types of concepts.

Some students retain definitions well but forget processes quickly.
Some students forget formulas fast but remember diagrams and visual
descriptions. The model does not need to know why — it just tracks
the patterns.

**What the model produces:**

At any moment, for every concept the student has encountered, the
system can say:

```
Mitosis                    → 82% strength  (strong, no action needed)
Mitotic Spindle Formation  → 45% strength  (review soon)
Cell Cycle Checkpoints     → 23% strength  (critical, review now)
DNA Replication            → 71% strength  (okay for now)
Meiosis                    → 38% strength  (review today)
```

This is not a guess. It is a prediction based on when the student
last studied each concept, how well they performed, and their
personal forgetting patterns learned over time.

---

### System 3: The Quiz Engine

**What it is:**

The decision-making system that determines which concept to test next,
what type of question to ask, and how to evaluate the student's answer.

**How it selects the next concept:**

The quiz engine considers four factors and weighs them together:

```
FACTOR 1: MEMORY URGENCY
━━━━━━━━━━━━━━━━━━━━━━━
Which concepts are closest to being forgotten?
A concept at 25% strength is more urgent than one at 70%.
The system does not want the student to lose knowledge 
they already invested time learning.

FACTOR 2: DEPENDENCY IMPACT
━━━━━━━━━━━━━━━━━━━━━━━━━━
Which concepts are prerequisites for other concepts?
If "cell membrane structure" is weak, and three other 
concepts depend on it, reviewing that one concept 
strengthens everything downstream.
This uses the knowledge map to calculate impact.

FACTOR 3: COVERAGE
━━━━━━━━━━━━━━━━━━
Has the student been tested on everything in the chapter?
Concepts the student has never been quizzed on get a 
boost in priority — the system needs data on everything 
to make accurate predictions.

FACTOR 4: RECENCY
━━━━━━━━━━━━━━━━━
Do not ask about the same concept twice in a row.
Space out related concepts. If the student just answered 
a question about mitosis, ask about something else before 
returning to mitosis. This mirrors how effective studying 
actually works — interleaving different topics.
```

The engine combines these four factors into a priority score for
every concept and picks the highest priority one.

**How it generates different question types:**

For each concept, the system can ask at multiple difficulty levels.
It chooses the difficulty based on the student's current memory
strength for that concept:

```
MEMORY STRENGTH HIGH (70-100%):
  → Ask APPLICATION or CONNECTION questions
  → The student knows the basics, so push them to think deeper
  → Example: "Your notes describe both G1 and G2 checkpoints.
    What would happen if a cell passed G2 with damaged DNA?"

MEMORY STRENGTH MEDIUM (40-70%):
  → Ask UNDERSTANDING questions
  → Reinforce the concept without being too easy or too hard
  → Example: "Explain the role of cyclins in the cell cycle
    as described in your notes."

MEMORY STRENGTH LOW (0-40%):
  → Ask RECALL questions
  → The student may have forgotten the basics — start simple
  → Example: "According to your notes, what are the phases 
    of mitosis?"
  → If they get this right, immediately follow up with a 
    harder question to strengthen the memory more
```

**How it evaluates answers:**

The evaluation is not just right or wrong. It is a detailed
comparison between the student's answer and the source material.

```
STUDENT'S ANSWER:
"Mitosis is cell division that produces two identical cells."

SOURCE MATERIAL SAYS:
"Mitosis is a type of cell division that results in two 
daughter cells, each having the same number and kind of 
chromosomes as the parent nucleus. It is typically divided 
into four stages: prophase, metaphase, anaphase, and telophase."

EVALUATION:
  ✓ Correctly identified that mitosis produces two cells
  ✓ Correctly identified that the cells are identical
  ✗ Missed the detail about chromosomes matching the parent
  ✗ Missed the four stages of mitosis
  
  Your answer covers the basic idea but is missing two 
  important details from your notes.
```

The student sees exactly what they got right, what they missed,
and where in their materials the complete answer is. They can
tap the reference to see the original text.

---

## The Hallucination Problem — How It Is Solved

This is the most critical design challenge. If the system generates
wrong information, students learn wrong things. That is worse than
having no tool at all.

engram uses six layers of protection:

```
LAYER 1: SOURCE GROUNDING
━━━━━━━━━━━━━━━━━━━━━━━━
The AI model is NEVER asked to recall information from its 
own training. Every task is accompanied by the relevant 
source text from the student's materials. The model is 
told: "Use ONLY the following text to create this question."
It works with what is in front of it, not what it "knows."

LAYER 2: EXTRACTION OVER GENERATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
For facts, definitions, and key terms, the system extracts 
directly from the source text rather than asking the AI to 
generate them. If the student's notes say "ATP is the energy 
currency of the cell," the system uses that exact fact. The 
AI model is only used for tasks that require language 
generation — creating questions, phrasing explanations, 
evaluating free-form answers.

LAYER 3: BOUNDED GENERATION
━━━━━━━━━━━━━━━━━━━━━━━━━━
When the AI does generate text, it operates within strict 
boundaries. It is given a chunk of source text and a specific 
task. It cannot introduce information from outside that chunk. 
If the source text does not contain enough information to 
create a meaningful question, the system moves to a different 
chunk rather than filling the gap with the AI's own knowledge.

LAYER 4: SOURCE CITATION
━━━━━━━━━━━━━━━━━━━━━━━━
Every piece of output — every question, every answer 
evaluation, every explanation — comes with a reference to 
the exact chunk of source text it was derived from. The 
student can always ask: "Where in my notes does it say this?" 
and the system shows the original text. If the student cannot 
find the referenced material, they know the system made an 
error. The system never asks the student to trust it blindly.

LAYER 5: UNCERTAINTY ACKNOWLEDGMENT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
If the student asks about something that is not covered in 
their materials, the system says so directly: "This topic is 
not covered in the documents you provided." It does not try 
to answer from general knowledge. It does not guess. It does 
not fill in gaps. It is designed to say "I don't know" rather 
than risk giving wrong information.

LAYER 6: STUDENT VERIFICATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
The knowledge map distinguishes between relationships that are 
explicitly stated in the source material and relationships that 
the system inferred. Stated relationships are shown as solid 
connections. Inferred relationships are shown as dashed 
connections and labeled "needs your confirmation." The student 
can confirm, reject, or edit any inferred relationship. The 
human stays in control of the knowledge structure.
```

**Can it still make mistakes?**

Yes. No system is perfect. The AI might occasionally generate a
question that subtly introduces information not in the notes, or
it might interpret a poorly written paragraph incorrectly, or it
might miss a nuance in the student's answer.

That is why Layer 4 (source citation) is the most important. Even
when the system makes an error, the student can catch it by
checking the cited source. The system is designed to be
transparent about where every piece of information comes from,
so errors are visible and correctable.

The student should always think of engram as a study aid,
not an authority. It helps them study more efficiently, but
they are still responsible for their own learning.

---

## The Hardware Problem — How Every Student Can Use It

Not every student has a powerful laptop. Many students worldwide
have a budget phone or an old laptop with limited memory and no
graphics card. The tool must work for them too.

engram handles this by splitting its work into two categories:

### What Always Runs on the Student's Device

These components are lightweight and run on any hardware, even a
budget phone:

```
DOCUMENT SCANNING
  Reading a PDF and identifying its structure.
  Requires no AI model. Just text parsing.
  Runs on anything.

TEXT CHUNKING
  Splitting text into meaningful pieces.
  Requires no AI model. Just logic.
  Runs on anything.

CONCEPT EXTRACTION (Basic)
  Finding bold words, headings, definition patterns.
  Requires no AI model. Just text pattern matching.
  Runs on anything. Runs instantly.

KNOWLEDGE GRAPH
  Storing and querying concept relationships.
  A data structure. Uses almost no memory.
  Runs on anything.

THE FORGETTING MODEL
  Mathematical calculations — decay curves and predictions.
  No neural network. Just arithmetic.
  Uses almost no resources. Runs on anything.

THE QUIZ SCHEDULER
  Deciding which concept to test next.
  Logic and scoring. No AI needed.
  Runs on anything.

THE STUDENT'S PROGRESS DATABASE
  All quiz results, memory strengths, study history.
  A local database file.
  Uses minimal storage and memory.
```

### What Needs an AI Model

These tasks require language understanding and generation:

```
GENERATING QUESTIONS from source text
EVALUATING free-form student answers
CREATING EXPLANATIONS when the student is confused
IDENTIFYING deeper concept relationships
```

These tasks can be handled in two ways — and the student chooses
which one works for their situation:

### Option 1: Local Model

The AI runs entirely on the student's device. No internet needed
after setup. Complete privacy.

```
WHO CAN USE THIS:
  Students with 8GB+ RAM and a decent processor.
  Most modern laptops from the last 3-4 years.
  Not suitable for budget phones or very old laptops.

HOW IT FEELS:
  Questions generate in 5-15 seconds on a regular laptop.
  Fast enough for a study session where you think between 
  questions anyway. Not instant, but usable.

WHAT RUNS:
  A language model that sits on the student's device.
  About 4-5GB of storage space.
  Uses RAM but not the graphics card.
```

### Option 2: Free API

The AI runs on a free cloud service. The student's device handles
everything except the language generation step, which gets sent to
the API for a fast response.

```
WHO CAN USE THIS:
  Any student with an internet connection.
  Works on phones, tablets, old laptops, anything.
  The student just needs to create a free account once.

HOW IT FEELS:
  Questions generate in 1-2 seconds. Feels instant.
  The fastest possible experience.

WHAT HAPPENS:
  The student's device does all the lightweight work locally.
  When it needs to generate a question or evaluate an answer, 
  it sends ONLY the relevant source chunks and the task to 
  the API. The API sends back the generated text.
  
  The student's full materials and progress data stay on 
  their device. Only the specific chunks needed for the 
  current task are sent — and they are generic textbook 
  excerpts, not personal information.
```

### Option 3: Bring Your Own API Key

For students who already have an API key from a service like
OpenAI, Anthropic, or any other provider. They enter their key,
and the tool uses their chosen provider.

```
WHO CAN USE THIS:
  Students who have access to paid API services.
  Maybe through university programs, personal subscriptions, 
  or developer accounts.

HOW IT FEELS:
  Depends on the provider. Usually 1-3 seconds per response.

WHAT HAPPENS:
  Same as Option 2, but using the student's preferred service 
  instead of the default free one.
```

### How the Choice Is Made

```
┌──────────────────────────────────────────────────────┐
│                                                      │
│   FIRST TIME THE STUDENT OPENS THE APP               │
│                                                      │
│   "How would you like to power the AI?"              │
│                                                      │
│   ○ Run locally on my device                         │
│     (requires 8GB RAM, works offline)                │
│                                                      │
│   ○ Use a free cloud service                         │
│     (works on any device, needs internet)            │
│                                                      │
│   ○ Use my own API key                               │
│     (I already have an account somewhere)            │
│                                                      │
│   "Not sure? The free cloud option works for          │
│    everyone. You can change this anytime."            │
│                                                      │
└──────────────────────────────────────────────────────┘
```

The rest of the system — the knowledge map, the forgetting model,
the quiz engine, the progress tracking — works identically
regardless of which option the student chooses. Only the
generation step changes.

---

## What engram Is Not

```
IT IS NOT A REPLACEMENT FOR UNDERSTANDING.
  It helps you study efficiently, but you still have to 
  do the work of actually learning the material.

IT IS NOT A SOURCE OF KNOWLEDGE.
  It only knows what your notes say. If your notes are 
  incomplete, the tool cannot help with what is missing.

IT IS NOT ALWAYS RIGHT.
  It can misinterpret your notes, generate imperfect 
  questions, or miscalculate your readiness. It is a 
  study aid, not an oracle.

IT IS NOT A SHORTCUT.
  It makes your study time more efficient by targeting 
  your weak spots. But you still need to put in the time.

IT IS NOT A CLOUD SERVICE.
  Your materials and your study data stay on your device.
  The tool is yours. Your data is yours. Nobody else 
  can see it unless you choose to share it.
```

---

## Why This Matters

The average student studies the same way students studied fifty
years ago. Read notes. Highlight. Re-read. Hope for the best.
The tools that exist today are either crude (flashcards),
expensive (cloud AI tutors that hallucinate and have no
personalization), or unintelligent (generic study apps with
no real understanding of the material or the student).

engram is different because it combines three things that
have never been combined in a single tool:

```
1. Understanding of the CONTENT
   What the concepts are and what they mean.

2. Understanding of the STRUCTURE
   How concepts depend on each other and which ones 
   are foundational.

3. Understanding of the STUDENT
   What this specific person is about to forget, based 
   on their personal learning and forgetting patterns.
```

All three running on the student's own device. For free.
Privately. Available to anyone who can clone a repository
and run two commands.

A student with a five-year-old laptop and an exam tomorrow
can have the same quality of personalized study guidance
that would otherwise require a private tutor.

That is what this project is for.

---

## The Core Principle

```
Every project that succeeds follows one rule:

Let the user start immediately.
Process the minimum needed to begin.
Improve quality in the background.
Never block the user from doing what they came to do.

A student drops a book. Thirty seconds later, they are 
studying. That is the standard. Nothing less is acceptable.
```

---

## License

MIT License — free for anyone to use, modify, and distribute.
```

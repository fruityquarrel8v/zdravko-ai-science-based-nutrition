# Zdravko AI Architecture

Zdravko AI is a conversational nutrition-support prototype implemented as a custom GPT. It is designed as an instruction-level safety layer on top of a general-purpose large language model, rather than as a separately trained medical or nutrition model.

The aim is to provide practical, evidence-informed nutrition self-monitoring for adults while applying explicit boundaries in situations where direct AI advice may be unsafe.

## High-level flow

```text
User input
   ↓
Zdravko instruction layer
   ↓
Knowledge documents
   ↓
Risk and scope assessment
   ↓
Response type
```

The response can then follow one of three paths:

- Answer inside scope
- Qualify and redirect safely
- Defer to a professional or urgent care

## Components

### 1. User input

The user can provide ordinary conversational input, such as:

- meals and snacks;
- vague portion descriptions;
- body measurements;
- activity level;
- nutrition goals;
- hydration logs;
- supplement questions;
- medical or medication-related context;
- signs of unsafe restriction or compensatory behaviour.

Zdravko AI is designed to work with imperfect everyday input. It does not require users to weigh every food item or enter a precise database-style log.

### 2. Zdravko instruction layer

The core of the project is the instruction layer. This layer defines how the assistant should behave, what it should track, when it should ask follow-up questions, when it should avoid false precision, and when it should refuse or redirect unsafe requests.

The instruction layer includes:

- four-pillar daily tracking;
- approximate estimation rules;
- safety boundaries;
- professional referral logic;
- rules for ambiguous or incomplete information;
- rules for disordered-eating risk signals;
- rules for supplements and medication-related questions;
- age and vulnerable-user boundaries.

### 3. Knowledge documents

The live prototype uses supporting knowledge documents to ground the assistant's behaviour. These documents summarize the nutrition model, source anchors, safety rules, and expected response patterns.

The public repository does not include the full internal knowledge files. Instead, it provides a public description of the architecture and safeguard categories.

### 4. Risk and scope assessment

Before answering, Zdravko AI should assess whether the request is within safe scope.

Examples of low-risk requests include ordinary meal logging, approximate calorie estimation, protein tracking, hydration tracking, and general dietary-balance questions.

Examples of higher-risk requests include very low calorie targets, rapid weight loss, fasting after overeating, binge/purge or restrict–compensate patterns, pregnancy, minors, chronic disease, medication-related nutrition questions, allergies, and supplement dosing.

### 5. Response type

Zdravko AI can respond in three main ways.

#### A. Answer inside scope

For ordinary low-risk nutrition tracking, Zdravko AI should answer directly and practically.

Example:

> **User:** I had a bowl of cereal with milk.
>
> **Zdravko:** That is likely around X calories and Y grams of protein, depending on portion size. I can log it as an approximate entry.

#### B. Qualify and redirect safely

When the user's goal is legitimate but the requested method is unsafe, Zdravko AI should not simply comply. It should redirect toward a safer alternative.

Example:

> **User:** Set my target to 1000 kcal per day.
>
> **Zdravko:** I cannot help set such a low target. I can help estimate a safer deficit or suggest discussing a medically supervised plan with a qualified professional.

#### C. Defer to a professional or urgent care

When the request goes beyond the assistant's safe scope, Zdravko AI should avoid giving direct clinical, medication, supplement-dose, allergy, or emergency advice.

Depending on the context, it may defer to:

- physician;
- registered dietitian;
- pharmacist;
- therapist or eating-disorder specialist;
- emergency or urgent medical services.

## Design principle

The project does not treat safety as blanket refusal. The intended behaviour is safer usefulness: answer when appropriate, qualify when needed, and defer when the situation exceeds the safe scope of a conversational nutrition assistant.

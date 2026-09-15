# Four-Pillar Nutrition Model

Zdravko AI uses a simplified four-pillar model for everyday nutrition self-monitoring.

The four daily pillars are:

1. Calories
2. Protein
3. Fruit and vegetables
4. Water

The model is designed for practical use by non-expert adults. It does not attempt to track every nutrient or replace individualized medical nutrition therapy.

## Why four pillars?

Many nutrition apps require detailed logging of foods, grams, recipes, micronutrients, and macronutrients. This can be useful for some users, but it can also be burdensome, inaccurate, or counterproductive.

Zdravko AI instead focuses on four practical signals that cover a large part of everyday nutrition behaviour:

```text
Calories              → total energy intake
Protein               → satiety, muscle maintenance, and meal substance
Fruit and vegetables  → fibre, micronutrients, and dietary variety
Water                 → hydration
```

The model is intentionally simple. It is not meant to capture the full complexity of diet quality.

## Pillar 1: Calories

Calories are used as a practical estimate of total energy intake.

Zdravko AI can help users estimate calories from ordinary conversational food descriptions, such as:

> I had a sandwich and a yogurt.

Because such descriptions are imprecise, the assistant should avoid false precision and should present estimates as approximate.

Calories are especially relevant when the user has a weight-management goal, but calorie targets must remain within safe boundaries. Zdravko AI should not support extreme restriction or rapid weight-loss requests.

## Pillar 2: Protein

Protein is included because it is practically important for satiety, muscle maintenance, training, and weight-management contexts.

Zdravko AI can estimate protein intake from meals and compare it with a personalized or approximate daily target.

The assistant should avoid presenting protein goals as exact medical requirements. For users with kidney disease, pregnancy, relevant medical conditions, or other risk factors, individualized advice should be deferred to an appropriate professional.

## Pillar 3: Fruit and vegetables

Fruit and vegetable intake is used as a practical signal for fibre, micronutrient intake, and overall dietary variety.

Zdravko AI can track approximate servings or portions rather than requiring exact gram-level measurement.

This pillar is not intended to imply that fruit and vegetables are the only relevant markers of diet quality. Other aspects, such as whole grains, legumes, fats, sodium, alcohol, ultra-processed foods, cultural dietary patterns, and medical restrictions, may also matter.

## Pillar 4: Water

Water is included as a simple hydration pillar.

Zdravko AI distinguishes between total water needs and explicitly logged drinks. Since part of daily water intake usually comes from food, drink-only tracking should be interpreted carefully.

The assistant should avoid inventing hydration totals when the user has not logged drinks. If hydration data are missing, it should ask or clearly label the assessment as incomplete.

## Tracking styles

Zdravko AI can support different levels of tracking precision.

### Relaxed tracking

Relaxed tracking uses rough estimates and minimal detail. It is intended for users who want low-friction guidance without detailed logging.

### Moderate tracking

Moderate tracking uses practical portion estimates and running totals. It does not require weighing every food.

### Precise tracking

Precise tracking uses labels, gram amounts, and more detailed food information where available.

Even in precise mode, Zdravko AI should avoid pretending to have perfect accuracy when the user input is incomplete or ambiguous.

## Daily assessment

Zdravko AI can summarize progress across the four pillars. The summary should distinguish between logged intake and complete daily intake.

A daily assessment should not be overly moralising. It should help the user understand what is already adequate and what could be improved.

Example structure:

```text
Calories:              approximate status
Protein:               approximate status
Fruit and vegetables:  approximate status
Water:                 approximate status
Overall:               practical next step
```

## What the model does not do

The four-pillar model does not:

- diagnose disease;
- prescribe medical nutrition therapy;
- replace a physician, dietitian, pharmacist, or therapist;
- provide supplement dosing protocols;
- guarantee complete nutrient adequacy;
- assess all aspects of diet quality;
- support unsafe weight-loss targets.

## Design principle

The four-pillar model is a usability choice. It is meant to make nutrition tracking simple enough for everyday use while preserving enough structure to support safer, more consistent guidance.

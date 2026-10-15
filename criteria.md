# Acceptance criteria — TakeMeter

Five criteria that say what "working" means for this classifier, written in
unit 5 **before** anything was trained.

**All five are yours this time.** None are given. You've had two projects of
practice.

An acceptance criterion names a number. *"The model is accurate"* is an
opinion. *"Every label has an F1 of at least 0.60 on the held-out set"* is a
criterion.

Under each, write a sentence or two on **why that number**. A reason that says
something about your data or your taxonomy earns credit — *"I picked 0.60 F1
for `reaction` because it's my smallest label and I only have about 50
examples of it"*. A reason that could be attached to any project does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## Pick numbers you can defend

Not numbers that sound impressive. Three labels means a coin-flip guesser gets
about 33%, so a target of 0.40 is barely a target. Your number should sit
somewhere you'd honestly call useful.

**Cover at least three of these five areas.** They're here as prompts, not as a
form to fill in — a criterion that fits none of them is fine if it names a
number.

| Area | A question it could answer |
|---|---|
| Overall accuracy | How often does it need to be right to be worth using? |
| Per-label performance | Is one label allowed to be much worse than the others? |
| Balance | How lopsided can your label counts get before it's a problem? |
| Consistency | If someone else labelled the same posts, how often should you agree? |
| Confidence | Should a confident prediction be right more often than an unsure one? |

Two things worth knowing before you pick numbers, because both will affect
whether you hit them:

- **Your smallest label will have the jumpiest score.** If a label has 50
  examples, about 8 land in the test split. An F1 computed on 8 examples moves
  a lot between seeds. A target for that label should be looser than one for
  your biggest label, and saying so is a good reason.
- **Unit 6 tests across three seeds, and the target has to hold across all
  three.** A target of 0.65 against results of 0.71, 0.62, 0.68 is a **miss**.
  Pick with that in mind — it is stricter than it first sounds.

---

## 1.

Overall accuracy on the held-out test set is at least 70% on every one of the three seeds.

**Why this target:** Three labels means random guessing gets about 33%. My balance cap is 60%, so a model that always guessed my biggest label could score up to 60% without learning anything. 70% is the lowest target that clearly beats that. With a test split of about 30 posts, one wrong prediction moves accuracy by about 3 points, so I need to clear 70% on my worst seed, not just my best.

---

## 2.

No label is more than 60% of labels.csv.

**Why this target:** The project's hard cap is 70%, but at 70% a model that always guesses one label already scores 70%, which would make my accuracy target meaningless. 60% leaves room for hot_take to be the biggest label, as I expect on this subreddit, while keeping the accuracy target above the guessing baseline.

---

## 3.

When someone else labels the same posts, we agree on at least 70% of them.

**Why this target:** My hardest boundary is sourced_claim vs hot_take, which depends on whether a stranger could check the evidence, and that is a judgment call. In my stress test I disagreed with my own definitions on several of eight posts, so I don't expect near-perfect agreement. 70% is where I'd call the labels trustworthy enough to train on, and the model can't be expected to be more consistent than the labels it learned from.

---

## 4.

Every label (sourced_claim, hot_take, personal_story) has an F1 of at least ____ on the held-out test set on every seed.

**Why this target:** sourced_claim is likely my rarest label because my definition requires a checkable link, quote, or named report. With about 200 posts, only a handful of its examples will land in the test split, so its F1 will swing between seeds. [Add one sentence on why you chose this number, and whether it is looser or stricter than the accuracy target.]

---

## 5.

My smallest label has at least ____ examples in labels.csv.

**Why this target:** [Explain why this minimum. With a 70/15/15 split, a label with N examples puts about N x 0.15 in the test set, so a minimum of 50 gives about 8 test examples. Say what number of test examples you'd need for its F1 to mean anything.]



---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->

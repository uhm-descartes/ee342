---
title: "Prosecutor's Fallacy"
published: true
morea_id: experience-profall
morea_type: experience
morea_summary: "Law, Fairy Tales, Overzealous bureaucrats"
morea_start_date: "2023-09-04"
morea_labels:
---

## Prosecutor's Fallacy

Here is a morbid story of a murder and accusing a potentially innocent
person. There is a town of 100,000 and a murder happens. Police
recover DNA from the scene, and Cinderella style, go from person to
person in the town, trying to match the DNA from the crime scene. They
find a match, but the guy turns out to be a seemingly upstanding
citizen, running 10 soup kitchens and 20 orphanages, and even the
detective (who has a long record of service and really knows what she
is doing) interviewing him thinks he is innocent. But the prosecutor
has seen many CSI TV shows, goes and hauls the poor guy to court,
roping in an expert witness who testifies that an innocent person's
DNA would match the crime scene with only probability
$$1/50000=.00002$$.

How to weigh these pieces of information?
Given the evidence, that is the person is a DNA match with the crime
scene, the judicial system needs to decide the conditional probability

$$ P(\textrm{ person is innocent } ∣ \textrm{ DNA match } ). $$

The expert witness however has the conditional probability

$$P( \textrm{ DNA match } ∣\textrm{ person is innocent } ). $$

In the expert testimony, the partial information is that the
person is innocent---and conditioned on it the chance of a DNA match
is rare. But it is quite different from the first conditional
probability where the partial information you see is the evidence, and
you need to decide if the person is innocent.

Indeed it is easy to see in this case they are very different. In
fact, you would guess that in that town, even if everyone were
innocent, an **expected** 2 people would match the DNA at the crime
scene (a formal statement of this will come in future modules). Just
because you caught a match among 100,000 doesn't really mean much when
you think about it---it just shows that the test is not good enough.

The word expected is highlighted above for a reason, and this is
something we will work on a lot in the course. This example is also
why we don't keep databases of everyone's DNA/fingerprints to solve
crimes like some vocal public figures near an election occasionally
want, why sane courts don't always weigh cold matches highly as evidence
and why pesky judges have always paid attention to how evidence is
collected (to the horror of the makers and consumers of CSI shows).

## Fairy tales and other stories

I love watching police procedurals (at least used to before my kids
were born). And as you may
guess, most shows are rampant with this fallacious reasoning. I won't
spoil those shows for you yet, but you will notice it henceforth :).

### Cinderella

The first opportunity to showcase this fallacious reasoning is the
fairy tale Cinderella. Here we have a prince who has decided, somehow,
that the probability a glass shoe will fit a random woman who isn't
Cinderella is very small. If you should tell this story to kids and
not make the Prince a complete idiot, you should introduce some other
piece of evidence (such as the Prince actually recognizing Cinderella,
in which case, why bother with the shoe?)---shoe fit alone finding
Cinderella is classic Prosecutor's Fallacy.

### Other stories


When I went to get vaccinated for Covid-19, one of the agents doing
the registrations there asked me my religion. Let us assume that the
agent wasn't just a karen/ken, but there was actually a Department of
Health policy to ask this question.

Someone from the Department of Health may have wanted to do outreach
to groups that may not have been getting vaccinated enough. Since this
is a class on probability and not public policy, let us also assume
such an outreach is a legitimate public service goal.  So, this
someone went ahead and decided to collect data about affiliations such
as religion at the vaccination centers. But does such a
rationalization make any sense?

Given the title for this page, as you may guess, the answer is
no. This is another example of Prosecutor's Fallacy. Can you see why?
What is the partial information here, and what is the conditional
probability you estimate if you asked people lining up for vaccination
their religion? If you indeed wanted data on which religious groups
you needed to do outreach for, what would you do?  
  
(PS: there was no policy from the Department of Health to ask questions
like this, I just got some overzealous karen/ken check me in.

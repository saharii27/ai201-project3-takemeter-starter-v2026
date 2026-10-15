# TakeMeter label taxonomy

## Question posts
Decision: I will only collect statement posts (posts that say something). I will skip posts that are mainly asking a question, like "should I take this offer?"

## Labels

### sourced_claim
Definition: Makes a point about the job market or tech industry and includes evidence a stranger could check from the post itself: a link, a direct quote, or a specific named report or announcement they could look up. The poster's own numbers and experience don't count.
Example 1: "Netflix plans to layoff 5% of workforce. https://www.reuters.com/business/media-telecom/netflix-plans-cut-5-its-workforce-puck-news-reports-2026-10-09/ Oct 9 (Reuters) - Netflix is planning to cut about 5% of its workforce, with an announcement expected as early as next week, Puck News reported on Friday, citing people familiar with the matter. ..."
Example 2: "Harvard just released another study about AI productivity in software engineering and it found there is no increase in productivity from using Claude code. The study itself is here https://fion.ac/jellyfish.pdf Overall they find that a.i. increases code review time and other bottlenecks even if it is decreasing the time code is generated."

### hot_take
Definition: States a confident claim or piece of news about the industry with nothing a stranger could check. This includes hearsay, vague sources ("a study showed"), and claims backed only by the poster's own experience.
Example 1: "Cto is planning on firing all junior and mid level devs"
Example 2: "Statistical rises in PR counts in the AI era are actually nonsense. Let me explain. My org heavily pressured us to get PR counts up. So, engineers did that by splitting up work into smaller items. ..."

### personal_story
Definition: Shares the poster's own situation or feelings without arguing a point about the wider job market.
Example 1: "I'm a doomer and I finally got a pretty cushy job. I feel so fortunate."
Example 2: "I never found a job two years after graduating college. I honestly didn't even try. I had a computer science degree... I barely applied for like 50 jobs a month before graduating and only got 1 interview..."

## Hardest boundary
Between: sourced_claim and hot_take
The borderline post: "Team Blind knows when you leave a company. ... Over the course of using this website for 10 years, I have never had to reverify my work email address... on 2 separate occasions where I have quit a job, Team Blind has popped up with an 'Automatic Email Re-verification'... Team Blind have https://business.teamblind.com which is something companies can pay for to get 'anonymised data' about their employees... it is not an anonymous platform."

Decision rule 1: A link, quote, or named report only makes it sourced_claim if a stranger could use it to check the post's main claim. If the evidence is just the poster's own inference or experience, it's hot_take, even if it includes a link or numbers.

Decision rule 2: If the post makes a claim about the wider job market or industry, it is not personal_story, even if it starts from the poster's own life.


1. sourced claim
2. sourced claim
3. hot take
4. hot take
5. personal story
6. personal story
7. hot take
8. hot take
Hesitated on: (post number, and the two labels I was choosing between)
Conflict pick: Option 1 or Option 2
for post 4 I thought it would go under sourced since it is talking about statistics. 
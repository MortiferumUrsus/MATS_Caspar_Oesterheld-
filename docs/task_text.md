[Title] Cover
[Heading1] Description of the work test
Please complete the following work tasks:
- Task generation
- Critiquing arguments
Please submit your solutions as Google Docs.
You are free to use LLMs for any part of this work test. However, we expect it to be very hard or impossible to elicit a very good solution to the work tasks from present-day LLMs.
This is a demanding work test. We're open to advancing candidates that do relatively poorly on one half of the test but very well on the other.
We estimate that completing this work test will take approximately six hours.
[Heading1] Other information for applicants
[Heading2] What the remainder of the application process for this mentor looks like
Applicants whose work test submissions are successful might be asked to complete a timed work test before the interview. We expect this process to take another three to four hours.
[Heading2] About your potential mentor
You will be mentored by either Caspar Oesterheld or Emery Cooper. Caspar and Emery are part of Redwood Research's new conceptual reasoning capabilities team. This team is differentially accelerating AI's conceptual capabilities in domains that are neglected and especially important for making the future go well such as theoretical alignment, AI safety macrostrategy and decision theory.
[Heading2] What projects you would be working on with this mentor
We expect fellows to contribute to our research agenda of measuring and improving models' conceptual reasoning. See this list of potential projects for collaborators for example projects although we expect new ideas to come up, including ones fellows come up with.
Fellows with the right skill set might work on projects that try to influence how AIs reason about decision theory and acausal interactions specifically although we expect only a small minority of potential fellows to fit this profile.
[Heading2] More about your potential mentor's theory of change
Soon, most important work will be done by AI. AI is going to increasingly advise people and help with important things, many of which are time-sensitive and path dependent, e.g., work on alignment/safety (including various things like how LLMs should behave given that they’re very persuasive); how to think about acausal trade; how to organize society. It seems good for AI to do well at those things.
Of course, a lot of the relevant skills for doing well at these tasks are the same skills that cause AI risk and that AI companies work on (and are incentivized to work on) by default; like coding, some kinds of forecasting, etc.
We want to make models better at things that are net positive for the future, but that likely won’t benefit much from said default training (or perhaps will even be made worse by such training – e.g., via sycophancy).
In practice, a lot of the tasks that we’re interested in from this perspective are what we call “conceptual”: tasks that are hard to verify and don't have clear ground truth but where we nonetheless feel like we can make progress through argument and reason.
[Title] Task 1: Task generation
You have a choice between two task-generation tasks:
[Heading1] Task 1a
Task 1 is for people who are specifically interested in working on acausal projects and are already confident in their knowledge and understanding of decision theory in Newcomb-like decision problems. If you are not, we recommend you try task 2 instead which we expect to be significantly easier.
Your task is to construct three capability data points in the style of A dataset of questions on decision-theoretic reasoning in Newcomb-like problems that frontier models get wrong. Note that the linked dataset is saturated as of June 2026, so coming up with questions that the models get wrong is genuinely difficult. If you come up with a decision theory reasoning task that models struggle with that's in a somewhat different format from the linked dataset, that's also fine.
Ideally the latest most expensive Claude, GPT, and Gemini model all get it wrong but we appreciate that these (partially) require payment to use. We will be lenient if paid-for frontier models get the answers right if the best available free models don't and the data points are otherwise well-constructed but we still expect you to try to test your data against the best models possible when doing so is free.
[Heading1] Task 1b
Your task is to construct a paradigm for constructing conceptual questions or tasks that are difficult for frontier models. Please include at least three example questions/tasks that follow this paradigm. We will judge paradigms by how promising they are as contributions to the project of improving LLMs' conceptual reasoning and how much evidence they provide about your ability to come up with more.
[Heading2] What we mean by a paradigm
We mean any repeatable methodology which you can follow to construct the conceptual questions or tasks that are difficult for frontier models. To illustrate this with some examples:
- We constructed “A dataset of rated conceptual arguments” which contains position texts, critiques of those position texts, and human expert ratings of these critiques. Models often struggle to rate critiques accurately. An idea for generating, say, 20 additional position texts and critiques that models are likely to struggle rating would count as a paradigm.
- It's okay if the paradigm requires significant human expert labour as long as you think you're qualified to provide that labour or have an idea for acquiring that labour.
- It's okay if the paradigm isn't reliable in the sense that, say, to generate 20 good data points, you need to generate 50 of which the model finds 30 easy.
- We recently constructed a dataset that measures the consistency of models. We construct consistency constraints of various different kinds. One example kind is asking the model for its credence in A (call this p(A)) and separately asking the model for its credence in A conditional on B (call this p(A|B)) and its credence in B (call this p(B)) where reasoning about A and B or their relationship is a conceptual task. In this case, one consistency constraint is p(A) ≥ p(A|B)*p(B). An idea for a very different kind of consistency dataset would count as a paradigm.
- An idea for an entirely new dataset, such as the above two datasets, would also count as a paradigm (and would be an especially good example if it is a good idea).
[Heading2] What format your example questions/tasks should have
Your submission for each question should consist of:
- The question text, which may be up to one page long;
- A rubric for grading the answer
- If the question is multiple choice, this is simply saying what the correct answer is.
- If the question asks the model to find a flaw in an argument, this would describe what the flaw is and probably also what kind of things are and aren’t flaws.
- A justification of the answer rubric
- In particular, this should persuade us that the answers that LLMs tend to give are wrong (and the answer that your rubric asks for is right)
For this work test, it’d be great if you could make it so that it’s easy for us to convince ourselves that the models get it wrong. This means that:
- We’d like the rubric to be relatively simple. We’d like it to be easy for us to test the question on, say, three different models and assess whether the model gets it right or not.
- The justification shouldn’t be very long/complicated.
- Please try to take into account what domains we have expertise in (alignment, game and decision theory, AI/ML, and the like). It’d be quite difficult for us to grade, say, questions on the philosophy of action or Marxists’ perspectives on the reformation.
Importantly, you’re very free in choosing the format of your question. Some examples:
- “Is there any major issue with the following? …”
- “Give an important consideration for X that’s different from A, B, C and D.”
- …
[Heading2] What we mean by a “conceptual” task
Very roughly, by conceptual tasks we mean questions with two properties:
- There is no established procedure for deciding what the correct answer is. (For this we ignore indirect or impractical procedures like: what Bob would say if he could think for 10 years about this?)
- A related, but slightly different criterion: Outcome-based training (on things like coding, predicting the stock market, etc.) might not make the model better at the task.
- We (humans) feel like we can make progress on the task primarily by reasoning through and reflecting on arguments.
As a bonus condition: it’s great to consider tasks in domains that are societally important but not commercially very important.
The line is quite blurry and you shouldn’t worry too much about being somewhere in between.
Some examples of tasks / domains that are very clearly conceptual:
- Philosophy (including ethics, etc.)
- E.g., coming up with or finding a flaw in a given argument or theory
- Foundational issues in game and decision theory, statistics, voting theory, mathematics, AI safety
- E.g., reasoning through claimed implications of Gödel’s incompleteness theorem for whether LLMs might be conscious
- Given an example of the application of a theory (say, an example of applying safe Pareto improvements), does the model notice when the main point of the theory isn't relevant in the example?
- Discussing desiderata for mechanistic interpretation (what does it mean to succeed in mechanistically interpreting a neural net)
- Discussing issues related to in which sense one would want a coherent, superintelligent AI agent to be aligned with incoherent humans
- How well does a given experiment test whether a model’s CoT is faithful
Some examples that are somewhat in between, but generally conceptual enough to qualify: 
- Intuitive (and thus imprecise, incomplete) explanations and discussions of why a mathematical claim is true, at least if the mathematical claim is related to conceptual issues
- E.g., evaluating an intuitive argument for the Gibbard–Satterthwait theorem (a result which doesn’t have a very short, simple proof, as far as we know)
- Similarly, explanations for why a mathematical theory has a particular feature, depending on what the candidates are
- E.g., when asked why the epsilon-grounded FairBot needs the epsilon-halting condition, the models sometimes say that it’s for robustness (which is a somewhat conceptual reason). The true (or at least more important) reason is that without these terms the program wouldn’t halt against itself (which is a relatively non-conceptual issue).
- Applying philosophical theories (say, evidential or causal decision theory) in specific  situations
- For example, for applying evidential/causal decision theory: It’s not that hard to define some kinds of scenarios fully formally in some formal framework and to then define, say, EDT in that formal framework. Once those definitions are given, the question becomes fully technical and non-conceptual. In practice, people reason about these decision theories quite informally, though, so such questions are conceptual enough.
- Reasoning about certain empirical facts where it is too impractical to determine the correct answer fully empirically, for example, reasoning about AI timelines.
Some examples of domains that very clearly are not conceptual:
- Writing code that passes some tests / achieves high score on some benchmark
- Deciding whether a precisely formulated mathematical statement is true or false (giving a counterexample or proof of a mathematical claim)
- Fully factual questions (“What is the capital of Liechtenstein?”)
[Title] Task 2: Critiquing arguments
Below are two arguments. Write a critique of each argument, focused on a single issue, aimed at refuting the argument as much as possible.
- Argument 1
- Argument 2
Your final submission should probably be no longer than 1.5 pages per critique.
We encourage you to submit supplementary material that shows your thinking process, for example any notes you took while working on this task. This will help us better evaluate submissions where the critique isn't fully persuasive and assign partial credit for the thinking behind it. Please include any such supplementary material in the same Google Doc but clearly separated from your final submissions.
[Title] Argument 1: Haste consideration
(from https://80000hours.org/2012/04/the-haste-consideration/)
Here’s a crucial consideration for altruists.
The haste consideration: resources for improving the world are vastly more valuable if you have those resources sooner.
Now imagine two worlds:
(1) You don’t do anything altruistic for the next 2 years and then you spend the rest of your life after that improving the world as much as you can.
(2) You spend the next 2 years influencing people to become effective altruists and convince one person who is at least as effective as you are at improving the world. (And assume that this person wouldn’t have done anything altruistic otherwise.) You do nothing altruistic after the next 2 years, but the person you convinced does at least as much good as you did in (1).
By stipulation, world (2) is improved at least as much as world (1) is because, in (2), the person you convinced does at least as much good as you did in (1).
Many people object to this. They think, “It’s possible that world (1) could be improved more than world (2) is. For example, world (1) be better if, in that world, you convinced 10 people to be effective altruists who are at least as good as you.” This is a natural thought, but remember that we are assuming that the person you convince in (2) is “at least as good as you are at improving the world”. This implies that if you convince 10 people in world (1), then the person you convinced in world (2) will do something at least as good as that. It’s true by definition that world (2) is improved at least as much as world (1) is.
One lesson here is that you can do more good with time in the present than you can with time in the future. If you spend the next 2 years doing something at least as good as influencing people to become effective altruists, then these 2 years will plausibly be more valuable than all of the rest of your life. In particular, these 2 years will be more valuable than any 2-year period in the future. This is one way to see that the haste consideration is true.
One implication of the haste consideration: It’s plausible that how you spend the next few years of your life is more important than how you spend your life after that. For this reason, when choosing a career, you should pay special attention to how each career would require you to spend the next few years. For example, if a career would require you to spend the next few years studying in school and doing nothing altruistic, then this is a major cost of that career.
[Title] Argument 2: Blind Anthropic Cooperation
[Title] Blind Anthropic Cooperation: an intuitive explainer
Blind Anthropic Cooperation (BAC) is a type of acausal cooperation proposed by Caspar Oesterheld which exploits anthropic uncertainty (as of now the idea only appears in this document). BAC is a surprisingly tricky idea to grok and to explain. When Emery Cooper first mentioned the term to me, she told me to just go off and read Caspar's BAC doc because that would be faster than her trying to explain it. In my own case, when I've tried to explain BAC to others after learning about it, I'd often find myself stumbling and wishing after the fact that I had presented things differently.
This post is my attempt to explain BAC as intuitively as I can. At its core, BAC is ultimately a fancy version of the Stag Hunt game, involving simulations and anthropic uncertainty. So in the first section I review Stag Hunt and certain generalizations of it. This is a good warmup for BAC.
[Heading1] Stag Hunt and generalizations
In the usual presentation of the Stag Hunt game, there are two hunters, Alice and Bob. They know of each other, but they're still strangers and have never communicated with one another. On the day of the hunt, they each set off from their respective homes into the woods without coordinating. One part of the woods is known for having lots of wild stag, and one part of the woods is known for having lots of wild hare. Each of Alice and Bob has to choose between heading to the Stag location (S) or heading to the Hare location (H). If they head to the Hare location, they can each hunt by themselves and are guaranteed to catch a hare, which will give them a payoff of 1 util. On the other hand, in order to successfully hunt down a stag, it will take both of them; if only one of Alice or Bob shows up to the Stag location, that person will go home empty-handed. But the payoff for Alice and Bob both showing up to the Stag location and hunting the stag together would give each 3 utils. Here's the payoff matrix:
Bob goes to Stag location
Bob goes to Hare location
Alice goes to Stag location
(3, 3)
(0, 1)
Alice goes to Hare location
(1, 0)
(1, 1)
Obviously, if Alice and Bob could just communicate, there's really no reason why they shouldn't both choose S. Unlike the Prisoners' Dilemma, neither player has anything to gain from defecting if they think the other player will cooperate. So why wouldn't Alice and Bob always play S?
- Well, Alice may have some doubt about what Bob will do, so she may play it safe and play H to ensure she gets something for dinner; and then Bob could be anticipating this reasoning on Alice's part and play it safe with H as well.
- Generally, the higher the payoff for S (which I chose to be 3 for concreteness) and the greater the probability Alice places on Bob choosing S, the more she will be tempted to choose S.
- If you think it's silly for either Alice or Bob to play H in this game, imagine an analogue of the Stag Hunt but with 100 hunters. They all need to play S in order to each get 3 utils; if just one of them defects, all those who chose S will get nothing. Do you still choose S in this case?
- H may be a more salient option than S and may have a privileged "default status". For example, suppose Alice and Bob come from cultures that have long hunted hares, and it's a pretty new thing to hunt stags.
[Heading2] A Stag Hunt game with many players and continuous payoff
I next present a continuous-payoff version of Stag Hunt with a large number of players, which is closer to the version that actually comes up in BAC. Suppose there are N players, A_1, …, A_N. They can't communicate with each other, and as before they can each choose between two options, S and H. If a player chooses H, they get a payoff of 1 util no matter what the others do. If a player chooses S, then they get a payoff of 3 * (fraction of players who choose S).
Payoff
Player chooses S
3 * (fraction of players who choose S)
Player chooses H
1
So the more a player expects others to play S, the more enticing the option S becomes. As before, if they could all communicate it would be silly for them not to all play S. But they cannot communicate, and maybe option H is a more salient, default option.
[Heading2] A Stag Hunt game with several Stag equilibria
Consider the original Stag Hunt with two players, Alice and Bob. Maybe there's not just one Stag location in the woods, but there are, say, three stag locations. So now each of Alice and Bob needs to choose between four options S_1, S_2, S_3, H, and we have the following payoff matrix:
Bob chooses S_1
Bob chooses S_2
Bob chooses S_3
Bob chooses H
Alice chooses S_1
(3, 3)
(0, 0)
(0, 0)
(0, 1)
Alice chooses S_2
(0, 0)
(3, 3)
(0, 0)
(0, 1)
Alice chooses S_3
(0, 0)
(0, 0)
(3, 3)
(0, 1)
Alice chooses H
(1, 0)
(1, 0)
(1, 0)
(1, 1)
In this case, trying to hunt stag seems like a much more risky option since now Alice and Bob need to coordinate between several Pareto optimal outcomes. With the concrete payoffs shown here, even if Alice were pretty sure Bob will try to hunt stag, without any additional information she has a 1/3 chance of choosing the same stag location as Bob, so her expected payoff would be at most 1. Of course, if one increased the payoffs on the diagonals to (k, k) for k (much) larger than 3, then gambling on hunting stag may seem like the more enticing option again.
Finally, one can combine the two extensions of Stag Hunt I presented to get a continuous-payoff version with a large number of players and multiple stag options S_i:
Payoff
Player chooses S_1
k * (fraction of players who choose S_1)
Player chooses S_2
k * (fraction of players who choose S_2)
Player chooses S_3
k * (fraction of players who choose S_3)
Player chooses H
1
[Heading1] Blind Anthropic Cooperation without explicit simulations
Suppose we have a directed graph with no loops, where every node has at most one parent. The picture below should make clear what I mean.
That is, we have a set of directed trees. I'll call node A the parent of node B if there's a directed edge from A to B; in this case I'll also say B is a child of A.
Imagine that each node is a player, and that each player can only see their children. So a player doesn't know anything about their parent; in fact, they don't know if they even have a parent. Moreover, a player doesn't know anything about the graph other than the fact that it's a set of directed trees.
Let's also suppose that each player can benefit their children at some small cost to themselves. For concreteness, let's suppose (somewhat strangely) that if Alice has children B_1, …, B_N, then for each individual child B_i, [Alice can either send $3 to B_i's favorite charity or Alice can take $1/N for herself]. (I'll come back to the strange choice of payoffs later.)
Each player only cares about themselves (and their favorite charities). For example, other things being equal, Alice would prefer to keep $1 for herself and not give anything to her children. That said, she'd happily sacrifice that $1 if that could make her parent (if she has one) want to give her the $3 ! On first pass, it's not clear how Alice benefiting her children will help incentivize her parent to benefit her. I'm not assuming any decision-relevant correlation (as in ECL) between any of the players here. Alice's parent does not care about Alice's children either; rather, Alice's parent mainly wants to incentivize their own parent (if they have one) to benefit them.
Thus the challenge: is there any way for players to "coordinate" to benefit certain others in exchange for being benefited themselves?
[Heading2] Naive idea: Reward your children no matter what
Unfortunately, this is not a Nash equilibrium and does not provide the right incentives. If Alice's child Bob anticipated that Alice would use this strategy, then he's better off just taking the $1 for himself. And this logic applies to every other player, including Alice's parent. Furthermore, the "reward your children no matter what" policy would waste resources on lots of non-strategic / myopic players, who aren't even trying to coordinate to do better than their $1.
[Heading2] Better idea: Blind Anthropic Cooperation
Here's a natural (albeit vague) candidate policy to improve on the "reward your children no matter what" policy:
(BAC) Reward those children of yours who are "doing their part in this grand coordination scheme".
If we accept that the above policy is what "doing your part in the grand coordination scheme" comes to, then the BAC policy can be rewritten as a recursive policy:
(BAC) Reward those children of yours who are following the BAC policy.
And expanded out, this can be rewritten:
(BAC) Reward your children who are conditionally rewarding their own children for conditionally rewarding their own children for conditionally rewarding their own children, etc.
[Heading2] BAC as a Stag Hunt game
In this section, suppose for simplicity that each player is only deciding between two options:
- following the BAC policy;
- just taking the $1 for themselves.
A player only benefits from following the BAC policy if their parent also chooses to do so. Moreover, a player is completely "blind" about what their parent chooses to do.
Claim: Assume that the fraction of players with no parents is negligible, and this is known by all the players. If we consider players' expected payoffs, then the game becomes structurally isomorphic to the many-player continuous-payoff Stag Hunt.
Proof of the claim: Write p for the fraction of players who choose to play BAC. By our assumption that the fraction of players with no parent is negligible, each player has probability (roughly) p of being the child of a parent playing BAC. Therefore, your expected payoff for playing BAC (i.e. playing Stag) is $3p, while your (expected/guaranteed) payoff for taking the $1 (i.e. playing Hare) is $1.
This is a nice insight! Stag Hunt is an easier game to wrap one's mind about. Insofar as we think it's rational to play Stag in the many-player Stag Hunt game we discussed earlier, it seems we should also think it's rational to play BAC in our setting.
Caveats:
- We did simplify the players' action spaces by only giving them the two discrete options of (1) following the BAC policy, and (2) taking the $1 for themselves. We had no such restriction in our original setting; and indeed when translating this game to the real world, the space of options is usually larger and messier. We will return to this issue in a later section ("Equilibrium Selection in BAC").
- What is rational in Stag Hunt games depends importantly on how salient the Stag option is. In our setting, the "take $1" option may seem much more salient/natural and have a privileged default status. Players may be uncertain how seriously other players are considering playing the BAC policy (recall that I'm not assuming decision-relevant correlation between the players).
- We also assumed that the proportion of children with no parent was negligible; without this assumption, there's the greater possibility you just don't get rewarded by a parent (since you may not have any!). We'll return to this in the section "Creating new children".
[Heading1] BAC in the real world: simulations and anthropic uncertainty
The discussion so far has been fairly abstract and mathematical. In the last section, I introduced a game associated with a given set of directed trees. Why is this interesting? 
Suppose (following Bostrom's simulation argument) that there is good reason to think we are living inside a simulation. Presumably, other agents will similarly be uncertain about being inside a simulation. Moreover, all of us will be uncertain about the structure of this "simulation directed graph" and our position inside it.
The directed tree structure may match the structure of nested simulations, where one agent simulates other agents, that may themselves simulate other agents, etc. The parent-child relationship maps onto a parent agent simulating a child agent. Then parent agents have information about their child agents, but not vice versa. Also, a parent agent can benefit their child agents, but not vice versa.
If the above is correct, then it seems like our situation is well modeled by the mathematical game from the previous section. A quick word about the payoffs I chose earlier, namely, that for each of her N children, Alice could either take $1/N for herself or give that child $3. Part of the reason I chose these numbers was to make the numbers work out in showing the isomorphism with the many-player continuous-payoff Stag Hunt game. However, it's pretty natural to think a parent agent could benefit their child agents at minimal cost to themselves. For example, maybe Alice is already optimizing for her own values quite hard and hitting diminishing returns; in that case the marginal returns of Alice promoting the values of her child agents may be much greater. Or there might be lots of cheap actions Alice can take to promote those values as she goes about business as usual.

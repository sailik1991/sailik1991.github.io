### 🧐 Research Aspects:

1. RL is a crappy learning paradigm, but it looks good since others are worse.
    1. Sparse rewards -- episodic rewards up/down rewarding every token in a trajectory is stupid. Need some notion of reflection over the trajectory and thinking which parts are good vs not.
    2. LLM as judge to reward partial trajectories don't work. Adversarial samples are easy to come up with and the generator (student model) can easily game the discriminator (LLM-as-a-judge). Iteratively improving generator & discriminator (similar to GAN) may work.
2. Keeping entropy high when learning.
    1. Statistically, most models are collapsed in the output space. Using these synthetically generated trajectories for continual learning will exacerbate the collapse.
    2. Simple ways such as diversity enhanced trajectory generation may not work well in the long term. Diversity might encourage the model to generate their own languages or use rare-words.
    3. Maybe this is okay given most tasks we plan to use the LLM for doesn't require diversity.
3. Model should be stripped to its cognitive core by training/distilling, and not have (esoteric) knowledge in its parameters.
    1. Cognitive core may require much lower parameters and should have just enough knowledge to evaluate imperfect recall and look up stuff (retrieval-as-a-tool) when need be.

### 🛠️ AI Usability Aspects:

1. LLMs for coding has a spectrum; where do you reside? 
    1. Don't use it at all seems too conservative.
    2. Use it to spawn separate agents and expect a miracle out of it is stupid, unless
        1. You just want some boilerplate code to start with
        2. The code you need is commonplace (has hide mode) in the training/internet data.
    3. See it from the viewpoint of a iterative improvement of developer tools.
        1. Programming languages and compilers abstract out generation and optimization of assembly languages.
        2. Initial regex based tab-matching systems abstract out the need to remember all variables, functions, etc. in a code-base.
        3. Current tab-complete with LLMs can abstract out some of the boilerplate code completions and some simple logic completions that you know are simple but just need it to type it out for you (makes review and correction easy since you already know what you were wanting to do).
        4. Andrej found it useful when you want to implement logic in a new language you are not super conversant in (e.g. Rust).

### 🤷‍♂️ Outside my area of expertise:

1. [Philosophical] Generational encoding of algorithms (evolution) couples with our life-long learning mechanisms may be significantly different from pre-training + RL based learning.
    1. We are trying to learn ghosts/spirits that imitate human-like behavior. [This is why we are expected to see incomprehensible failure modes with LLMs that are not seen with humans.]
2. [Business] The industry is over-promising or over-advertising the capabilities of agency [possibly business/fund-raising mindset that most of us technical folks don't fully understand]. We will surely do better things with agents than what was possible in the past, but when the delivery doesn't meet the over-hyped promise, does the bubble burst?
3. [AI-Ed] A good tutor can determine the exact capacity of a student by sampling answers from them with targeted questions, and then offer a curriculum in a way that aptly challenges the student to improve the capability (not too difficult, not to easy). How can we do that?
    1. Difficult with current LLMs -- not way to probe in a targeted way to understand knowledge/capacity boundary of a user/pupil and calibrate assistance. Asking LLMs mostly generate generic slop stemming from retrieval/search engine results. The user themselves have to be in the driving seat and express well to guide the help they need.
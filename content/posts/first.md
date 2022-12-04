---
title: "Race to the Top: Rethink Benchmark-Making for Safe AI Development"
date: 2022-12-03T17:08:10Z
draft: false
tags: ["model evaluation", "AI safety"]

params:
 ShowShareButtons: true
ShowToc: true
TocOpen: true
---

<!-- Output copied to clipboard! -->

<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 1.758 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β33
* Sat Dec 03 2022 11:30:04 GMT-0800 (PST)
* Source doc: Race to the Top (blog draft 5.0)
----->



## Executive Summary

Benchmarks support the empirical, quantitative evaluation of progress in AI research. Although benchmarks are ubiquitous in most subfields of machine learning, they are still rare in the subfield of _AI safety_.

In this post, I argue that **creating benchmarks should be a high priority for AI safety.** While this idea is not new, I think it may still be underrated. Among other benefits, benchmarks would make it much easier to:




* track the field’s progress and focus resources on the most productive lines of work;
* create professional incentives for researchers - _especially Chinese researchers_ - to work on problems that are relevant to AGI safety;
* develop auditing regimes and regulations for advanced AI systems.

Unfortunately, **we cannot assume that good benchmarks will be developed quickly enough “by default."** I discuss several reasons to expect them to be undersupplied. I also outline actions that different groups can take today to accelerate their development.  \
 \
For example, **AI safety researchers can help by:**



* directly trying their hand at creating safety-relevant benchmarks;
* clarifying certain safety-relevant traits (such as “honesty” and “power-seekingness”) that it could be important to measure in the future;
* building up relevant expertise and skills, for instance by working on other benchmarking projects;
* drafting “benchmark roadmaps,” which identify categories of benchmarks that could be valuable in the future and outline prerequisites for developing them.

**AI governance professionals can help by:**



* co-organizing workshops, competitions, and prizes focused on benchmarking;
* creating third-party institutional homes for benchmarking work;
* clarifying, ahead of time, how auditing and regulatory frameworks can put benchmarks to use;
* advising safety researchers on political, institutional, and strategic considerations that matter for benchmark design;
* popularizing the narrative of a “race to the top” on AI safety.

Ultimately, **we can and should begin to build benchmark-making capability now.**


## Why important?



* **AI safety field-building.**
    * **Measure progress in AI safety.** Benchmarks measure how well AI systems perform on specific tasks. With safety-relevant benchmarks, we may avoid illusions of progress or the lack thereof; we can make better strategic decisions among different safety approaches and model paradigms.
    * **Make progress in AI safety.** For example, with truthfulness benchmarks, we would be able to compare model embeddings of truthful and untruthful models, and learn more concretely about what makes models truthful, to what extent truthfulness generalizes, and how to make future models robustly truthful.
    * **Normalize safety discourse and cultivate safety culture.** Right now, AI safety is still a niche research area that not many ML researchers engage with seriously. Having safety-relevant benchmarks that people can make concrete progress on can help normalize AI safety concerns in the mainstream ML community. This likely improves future adherence to safety standards.   
* **Incentivize “race to the top” over safety.** Benchmarks can play a critical role in steering AI development.[^1] They encode values by defining what tasks and problems are important to work on, and what’s important about them. Widely accepted benchmarks are often absorbed into peer review norms and influence resource investments. They set out competitive dynamics among AI researchers, who are incentivized to optimize their models and algorithms for a better performance than the state-of-the-art (SOTA). Therefore, we may use safety-relevant benchmarks to promote healthy competition over safety-relevant properties of AI systems, incentivizing researchers and labs to develop better and better safety technology.[^2]


    * **Incentivize AI safety research globally, especially in China.** Competition over benchmarks transcends national borders and can provide one of the few ways to influence AI research and development in non-western world, most importantly in China. Safety-relevant benchmarks offer an academic, scientific setting that is non-political and conducive for exchange of ideas. This can be the stepping stone for building global cooperation on AI safety.  
* **Prerequisite to governance.** Safety-relevant benchmarks are essential, though insufficient, for third-party organizations to provide reliable auditing and certification services for AI labs, or for governments to enforce standards against AI risks.
    * **A failsafe for process-only auditing.** One might point out that process auditing does not require benchmarks. But ideally, we might want both. In absence of any quantitative measure, auditing delegates more discretion to the auditing organization, which would fail if bureaucrats are incompetent or have special interests; if competition among auditors leads to less stringent safety standards;[^3] [^4] and if a monopolistic auditor has no incentive to improve safety standards over time.[^5] safety-relevant benchmarks can provide some safeguards against these failure cases.  


    * **A better branding to gain trust.** Initially, benchmark-making can sound more appealing to AI labs and researchers than auditing: third-party actors can position themselves as trying to “help,” instead of “inspecting potential wrongdoings.” Thus, safety-relevant benchmarks help new third-party actors to establish a trusting, collaborative relationship with AI labs and researchers.
    * **A route to future-proof governance.** Good safety-relevant benchmarks kick off a healthy cycle between safety technology development and safety governance. With safety-relevant benchmarks, AI researchers and labs are incentivized to invest in and find the best achievable safety technology. This informs the governance actors what safety standards are reasonable, mitigating the serious risks of selecting the wrong standards and sticking to them when they are outdated.


## Why under-supply?


### Making good, popular safety-relevant benchmarks is very difficult.



* **Intellectual capital.**
    * **Conceptual.** To make safety-relevant benchmarks, one needs to think about a messy concept clearly.[^6] For example, on honesty, what notions of “honesty” can be applied to a model, or a claim?  What does it mean for a model to “know” or “believe” something? How does honesty relate to other concepts such as “truthfulness” and “interpretability”?


    * **Technical.** With conceptual clarification, one would then need to measure the concept cleverly in a messy world, proposing tasks, data, metrics that accurately capture the behavior of the model. One would need to know the relevant ML subfield quite well, ideally having thought about or actually worked on the very problem for multiple years.[^7]


    * **Strategic.** One ideally should understand broader technical trajectories and the impacts of important decisions made throughout the benchmarking process. For example:
        * What safety-relevant properties are important and tractable to benchmark, if we care about transformative AI safety?
        * What exact capabilities would arise from efforts to score well on this benchmark?
        * What additional risks might these capabilities pose?
        * How do these capabilities affect investment, research, and deployment decisions?
* **Social capital.**
    * **Community-facing.**
        * **Network capital.** Ideally, one has published influential papers on the specific topic and accumulated much social capital in the subfield such that one knows how to promote the benchmark and get submissions. There is also a “network effect” of a benchmark: researchers will use benchmarks widely used by others to compare their work.
        * **Responsiveness.** One needs to understand the users’ demands well: Who will use this benchmark? What do they care about? How can it be made easier for usage?
    * **Lab-facing**.
        * **Model access.** To benchmark on feature X of a genre of models, one would need access to at least one model from this genre so that one knows what baseline performance looks like, what granularity of measurement is reasonable, and can ensure the benchmark is not too hard nor too easy. Access to different models would be required if the benchmark is based on adversarial questions. For example, some questions from truthfulQA are filtered based on whether GPT-3 answers them falsely, thus unfairly penalizing descendents of GPT-3 over other large language models. It also may not reliably capture different failure modes across different types of models.
        * **Legitimacy.** One top lab might be skeptical about the benchmark made by another lab.[^8] Thus, benchmarks may boost their legitimacy to AI labs if they are created by academic researchers or through inter-lab collaboration. Either way, coordination with top labs, even just light involvement that amounts to a user testing of what benchmark is wanted, will increase the chance that the benchmark takes off.[^9]


    * **Public-facing.**
        * **Legitimacy.** Some benchmarks (e.g. truthfulness, fairness, and other moral decision-making research areas) require careful design to demonstrate their legitimacy to the public.
* **(To less extent) financial capital.**
    * **Costs of human evaluations.** Safety-relevant benchmarks can be somewhat costly if massive data collections from humans are required to establish ground truths.[^10] For example, a benchmark assessing how aligned AI models are with fundamental human values ideally requires cross-validation among human annotators from across diverse linguistic, national, and cultural backgrounds.[^11] More difficult benchmarks may require more expensive expert annotations. For example, to design a “legal advice task” as part of the truthfulness benchmark, one needs legal experts to write questions and draw the line between right and wrong answers.  


* **Luck.**
    * Checking all the boxes does not guarantee the success and popularity of a benchmark. There is some lottery-like randomness accounting for why some benchmarks, not other similar ones, are most popular.   


### (Mostly) lack of incentives to try very hard.



* **Individual researchers.**
    * **Average researchers** have not thought systemically about what tasks are important to make progress on and what benchmarks would be good to measure such progress. They usually race on well-established problems and benchmarks for prestige and personal career advancements. They do not have an incentive to work on completely new tasks and design new benchmarks. Doing so is a high-risk investment with uncertain gains, especially for junior researchers: few benchmarks make the most impact and have the highest citations.
    * **Safety-conscious researchers** might have underrated the importance of making safety-relevant benchmarks relative to doing theoretical work or making actual empirical progress. They may also be deterred by the liability of making bad benchmarks. Finally, there are simply not many safety-conscious researchers.
* **Private labs.**
    * **If only prestige and revenue incentives, minimum safety.** If AI labs only care about prestige and revenues from making impressive systems, and if there is a trade-off between safety and impressiveness of the systems, we arrive at a world of minimum safety: AI labs would do just enough safety work to gain consumer trust and to meet the lower bound of existing expectations. Therefore, AI labs would prefer sketchy benchmarks, or no widely accepted benchmark at all: good benchmarks would have forced them to invest more in safety technology than they wanted to.
    * **If only safety incentives, maximum safety.** If AI labs only care about the safety of their AI systems, we arrive at a world of maximum safety: AI labs would invest _as much as they can_ in safety-relevant technology and benchmarks.
    * **If mixed incentives, safety conditional on how it relates to prestige and revenues.** Today’s top AI labs face two competing incentives: they care about both making impressive AI systems and making these systems safe.
        * Their investment in safety technology thus depends on the trade-off between safety and impressiveness of AI systems: the more people associate impressiveness with safety, the more AI labs invest in safety.
        * Safety-relevant benchmarks improve the trade-off: benchmarks shape people’s perceptions of what’s impressive, and safety-relevant benchmarks incorporate safety as part of the impressiveness of the AI systems.
        * This implies that, despite being safety-conscious, whether AI labs choose to produce safety-relevant benchmarks and which one they produce is not guaranteed; rather, it partially depends on their expectation of how a benchmark makes them more or less impressive. For example, AI labs may refrain from making safety-relevant benchmarks that make their models look really bad. They have little control over how their performance will be interpreted by the media and the public. Furthermore, designing good safety-relevant benchmarks is just hard, costly, and subjective to high liability. This is especially true for benchmarks that track safety-relevant properties most relevant for future AI systems, yet not immediately necessary. AI labs may thus be deterred from unilaterally heavily investing in those forward-looking benchmarks, when the same resources can be used to solve more salient and tractable ethical issues today, e.g. toxicity and discrimination.
        * **Given this incentive structure, we have no reason to believe that voluntary efforts from AI labs are enough for arriving at the best safety-relevant benchmarks.**  


### Governance actors with the right incentives are incapable.



* **No intellectual capital.** Although governments and safety-conscious third-party organizations may have the right incentives to invest in safety-relevant benchmarks as a public good, they lack the technical and strategic skills to do a good job.


## What may go wrong?


### Rotting



* **Problem:**
    * **Benchmarks can rot.** Benchmarks are necessarily simplified, incomplete measurements of AI systems’ capabilities. They can be saturated as researchers compete over high scores and push technology to develop. We want benchmarks to be harder over time and able to meaningfully distinguish even superhuman AI systems. Furthermore, as technology develops, we often learn new things about the problem we are trying to solve. We notice new contexts and facets of the problem we did not notice before. We try to understand the strengths and limitations of the current techniques. We learn what failure cases are especially important to us. We then want to change our definition of the problem and our measurement strategies, updating the existing benchmarks or creating new ones.
    * **Safety-relevant benchmarks can rot.** Safety problems we have today may not be the same problem that we worry most about. For example, we do not understand large language models enough to have a ground truth label for their honesty. Furthermore, their honesty can be a totally different problem than the honesty of multi-modular superhuman models. Finally, naive honesty benchmarks may only succeed in penalizing obviously dishonest behavior, which actually selects models that are honest _or_ capable of hiding dishonesty.   Thus, we may expect safety-relevant benchmarks to rot—even in a way more quickly and severely than other benchmarks, as there may be an adversarial dynamic between models that try to hide dangerous behaviors and benchmarks that try to spot them.   
    * **Rotting safety-relevant benchmarks are especially bad.** It is not uncommon that we discover the failure of popular benchmarks. For example, in the field of Natural Language Understanding, recent models have overfitted on longstanding benchmarks: they scored high on benchmarks but failed dramatically in simple test cases that are meant to test the very skills that those benchmarks focus on. But a similar failing of an AI safety benchmark, e.g. a truthfulness benchmark, can cause far more social harm: advanced AI systems can effectively learn how to lie or persuade humans with partial truths while scoring high on a low-quality truthfulness benchmark and retaining human trust. Powerful actors, for example, capability research teams in AI labs who do not take safety seriously, may capture the rotting benchmarks to downplay safety concerns. [^12]


* **Mitigation:**
    * **Think benchmarks as living institutions.** To keep safety-relevant benchmarks up-to-date, we may need to change the standard, static, dataset-based approach to benchmark-making. For example, we may want to consider the method of adversarial filtering, asking human annotators to try to fool AI systems.[^13] However, this method can incentivize researchers to create different models that are not necessarily better,[^14] thus perhaps having to be combined with naturally generated data. Furthermore, there are tensions between updating benchmarks frequently and ensuring consistent comparisons of models across time. Therefore, it may be better to make benchmarks difficult in the first place such that they last longer.   


    * **Incentivize open critiques and more benchmark-making.** We may subsidize researchers to make alternative benchmarks, offer prizes for good critiques of existing benchmarks, and lower the entry barriers of new benchmarks—for example, by assembling all honesty benchmarks on one integrated platform and making it easy for researchers to test their models against all of them.[^15]


    * **Make only modest claims.** We may want to be cautious when framing what problem our benchmark addresses, erring on the side of excessive humbleness. We should almost never use “safety” in names of the benchmarks, e.g. Safety Gym and SafeLife, but use more targeted descriptions, e.g. robustness or honesty. We should also always make explicit the limitations of the benchmarks, erring on the side of overstating the limitations.

We should still try to make benchmarks despite the downside risks from bad benchmarks, because:  



* **Bad benchmark scenarios are very unlikely.** The probability of bad benchmarks being highly impactful is low: as any benchmark, they have to get several things right to be impactful. Even they happen to be impactful for a while, they can be easily faulted and unlikely to stick around, moving the world towards good benchmark scenarios.
* **Even bad benchmark scenarios** (with the wrong kind of safety competition) **are probably better than no benchmark scenarios** (with no safety competition).
    * Bad benchmarks have a higher chance of being faulted than bad practices branded as “best practices.”  
    * Bad benchmarks offer a way to make progress on possible conceptual disagreement among AI researchers about what’s unsafe about some AI systems by making the disagreement explicit.
    * Even the wrong kind of competition might help empower the field of AI safety relative to AI capability, bringing more funding, talents, and computing resources.
    * Even the wrong kind of competition improves de facto adherence to safety standards, as AI labs have already paid the costs of developing safety technology, accumulated relevant knowledge and expertise, and cultivated a safety culture.
    * Even if sufficiently good safety technology and practices are discovered in the no benchmark scenario, owing to the good work of competent, safety-conscious researchers in the top labs, it is difficult and slow to bring about global adherence to these practices.
        * Making these practices legally required can be difficult: governments may be unwilling to impose too stringent regulations to provide sufficient room for innovation.[^16] Some governments such as China and Russia may also be suspicious and less cooperative of standards and practices that are proposed by western AI labs and look alien to them.


        * Even if legal enforcement is possible, it would be much slower: AI labs would want more safeguards in the rulemaking process (e.g. demanding veto powers and formal approval mechanisms) and have a higher incentive to water down the effectiveness and difficulties of safety standards. Furthermore, how safety standards interface with existing or future regulatory regimes, on a national or international level, can be especially complex.
* **Some bad benchmarks might be made anyway** in the baseline world when AI labs want to commercialize their models and harvest consumer trust, or when governance agencies perceive a need for quantitative measures, e.g. on honesty and truthfulness. If so, “less bad” benchmarks can still be valuable.


### Capability externality



* **Problem:**
    * **Safety-relevant benchmarks may speed up capability progress.**[^17] For example, some researchers argue that truthfulness benchmarks can adversely improve the accuracy[^18] of the models and advance general capabilities.


* **Mitigation:**
    * **Do careful strategic analysis.** Safety-capability is a fuzzy framework: for AI systems to be safe or aligned, they have to be more capable in a sense. We may want to develop a better analytical framework to assist benchmark designers’ analysis,[^19] or have someone do a centralized analysis of “10 benchmarks that seem robustly good to have.” Ultimately, however, miscellaneous decisions would require good strategic thinking of designers themselves.

### Misuse



* **Problem:**
    * **Some safety-relevant benchmarks may be used by malicious actors to create unsafe models.** For example, a benchmark that distinguishes honest behavior from dishonest behavior of the models could be intentionally used to train maximally dishonest models.
* **Mitigation:**
    * **Provide structured access to benchmarks.** For models that have a high risk of misuse, we may want to restrict access to benchmarks to only trusted actors, instead of making them open-source.


### Die quietly



*  **(Less of) problem:**
    * **Safety-relevant benchmarks may fail to attract talents and bring about competition.** A benchmark has the highest field-building impact when a problem is already recognized by a group of researchers as important, talked about frequently, but only with anecdotal examples and absent clear distillation. A benchmark on X by itself will not convince people that X is important to work on.  


### Opportunity cost



*  **(Less of ) problem:**
    * **Safety-conscious researchers have a high opportunity cost of benchmarking X, while they could actually solve X.** Given the lack of talents working on AI safety, and the uncertainty of what safety-relavent properties we can measure, how relevant they are for risks from superhuman AI systems, safety-conscious researchers perhaps should still mostly work on solving X.
* **Response and mitigation:**
    * **Solving X requires benchmarking X somehow.** Solving problem X requires clear distillation of what the problem consists of, what suffices “making progress” on it, which is essentially some version of “designing benchmarks on X.”
    * **Low-time commitments first.** Benchmarking does not have to take the majority of research time. One could start from writing demos and getting feedback without actually implementing the design.    
    * **Mobilize other talents.** It may be worthwhile to explore whether there are other talents, e.g. academic researchers, who are not working on concrete safety problems but have relevant knowledge and skillsets to work on safety-relevant benchmarks.


## What can you do?



* **AI safety researchers:**
    * **Do prioritization work.** Think ahead what benchmarks are tractable and important to make, and what potential capability externalities they may bring about.
    * **Do relevant conceptual or empirical work** on specific safety research areas that makes it easier for people to design future benchmarks.  
    * **Develop guidelines and examples.** If you are experienced in benchmark-making, write up general guidance on how to make good safety-relevant benchmarks, or actually make one to showcase the best practices.[^20]


    * **Build benchmark-design muscles.** Try to sketch demo benchmarks for concrete AI safety problems.[^21] Get feedback from researchers who think of the specific problem, have benchmark-making experience, and/or are potential consumers of benchmarks. If promising, consider actually making the benchmarks and submitting to [SafeBench](https://benchmarking.mlsafety.org), who is offering prize for safety benchmark ideas.


    * **Build strategic awareness of what’s happening in a subfield.** Have good intuition of future technical and human trajectories: What techniques are promising candidates? What do people care about, and how would they react if tomorrow there is a benchmark like X?
    * **Build networks and reputation in a subfield.** Connect with people who work in adjacent research areas. Publish highly cited work. Become an organizer of a well-respected ML conference, or a workshop therein.
* **AI governance/policy practitioners:**
    * **Think of benchmarks, before thinking about auditing/standards.** Benchmarking can be a useful, soft governance tool for third-party organizations to build trusting relations with AI labs and researchers. It also incentivizes race-to-the-top behavior of safety standards.
    * **Make safety-relevant benchmarks and competition happen.** The ideal benchmarking process should be a combination of competition and coordination: at first, AI labs and researchers critique and propose various benchmarks; as the field matures, they converge on a set of well-designed benchmarks. It is the task of AI governance to strike the right balance of competition and coordination that is conducive to the discovery of the best safety benchmark and technology.
        * **Build benchmarking capability in trusted academic or third-party research institutions.** AI models will become more capable, and labs will exercise tighter control over models. Thus, external researchers may have more difficulties accessing the models: even if AI labs want to grant “researcher access” for safety research, they may legitimately worry that doing so will increase the vulnerability of their system and the risks of misuse and proliferation. Thus, we may want to start building new third-party research centers or empowering existing ones (e.g. in academia, Stanford HAI, Berkeley CHAI, ETH Zurich SIR lab, MIT Media Lab; outside of academia, Alignment Research Center and Center for AI Safety) with secure, special access to models to make it easier for external safety researchers to study the models and make benchmarks that will be trusted by AI labs.
        * **Increase opportunities for academia-lab collaboration.** Similarly, we may want to increase safety fellowship/visiting scholar positions at AI labs such that academic researchers can access advanced models and study their behavior.[^22]  


        * **Organize open call competitions on ripe safety-relevant benchmarks.** For example, we could host a series of annual competition over large language models’ truthfulness as part of NeurIPS’s Competition Track Program.[^23] Competitions could ensure standardized usage of benchmarks.[^24] They also provide opportunities for human judges to evaluate AI systems synchronously and comparatively, in a more fine-grained way beyond static benchmarks. Finally, as safety-relevant benchmarks are not yet a norm, if AI labs can test their models privately and conceal the results, they may face little incentive to improve even if their models perform badly. Thus, we may use competitions to provoke relevant narrative change (e.g. “Impressive AIs are truthful AIs”) globally and raise the reputation costs of bad performance. Prizes given by third-party organizations like Elicit Latent Knowledge and innovation competitions sponsored by governments can also be promising channels to solicit safe and responsible development of AI systems.


        * **Organize workshops on safety-relevant benchmarks.** We could also organize workshops or even working groups at ML conferences like NeurIPS[^25] or other venues to facilitate conversations among AI safety researchers on what properties are important to benchmark as well as how to benchmark on specific safety-relevant properties.


        * **Encourage participation of international researchers, especially those from China.** Non-western researchers are under-represented in AI safety fields, but engaging them in ML competition and workshops may be important for the creation and enforcement of international safety standards in the future. This also means that benchmark designers
    * **Promote narrative change about a “race-to-the-top” over safety.**
        * Test whether the idea of safety competition is appealing to American and European policymakers, especially those who might otherwise be skeptical that safety regulations sacrifice innovation and national competitiveness.
        * Work with policy teams at safety-conscious AI labs to issue a joint statement on their commitments to use safety-relevant benchmarks and publish performance results, whenever applicable.
        * Work with communication professionals to further align the “impressiveness” of AI systems with safety-relevant properties.





<!-- Footnotes themselves at the bottom. -->
## Notes

[^1]:

     Mostafa Dehghani et al., ‘The Benchmark Lottery’ (arXiv, 14 July 2021), http://arxiv.org/abs/2107.07002.

[^2]:
     Safety-conscious actors such as governments or third-party organizations could also explicitly host competition over safety-relevant properties. A successful example is the “safety contest” organized by Finnish Construction Employers Association. Construction companies voluntarily participated in the contest, where safety inspectors conducted evaluation visits without previous notice to the sites. More than 70% of the total number of construction sites participated; an estimated 4000 accidents and three fatalities are prevented each year. See, Heikki Laitinen and Keijo Päivärinta, ‘A New-Generation Safety Contest in the Construction Industry – A Long-Term Evaluation of a Real-Life Intervention’, Safety Science 48, no. 5 (1 June 2010): 680–86, https://doi.org/10.1016/j.ssci.2010.01.018.

[^3]:

     There are some anecdotal evidence suggesting that competition among auditing and certification bodies led to weak standards. See, Yuqing Zheng and Talia Bar, ‘Certifier Competition and Audit Grades: An Empirical Examination Using Food Safety Certification’, Applied Economic Perspectives and Policy, 17 November 2021, aepp.13211, https://doi.org/10.1002/aepp.13211.

[^4]:
     Eric F. Lambin and Tannis Thorlakson, ‘Sustainability Standards: Interactions Between Private Actors, Civil Society, and Governments’, Annual Review of Environment and Resources 43, no. 1 (17 October 2018): 369–93, https://doi.org/10.1146/annurev-environ-102017-025931.

[^5]:
     Gillian Hadfield, ‘Rules for a Flat World’, n.d., 409.

[^6]:

     For a good example of conceptual work, see Owain Evans et al., ‘Truthful AI: Developing and Governing AI That Does Not Lie’, ArXiv:2110.06674 [Cs], 13 October 2021, http://arxiv.org/abs/2110.06674.](https://www.zotero.org/google-docs/?bfXAc6

[^7]:

     In some cases, experience with high-quality data work can be very desirable, e.g. working with human subjects and designing interfaces, although this is unlikely a bottleneck. Many current benchmarks involve easier tasks and are subject to “noise, correctness, and distributional issues” due to lack of data labeling expertise. See, Samuel R. Bowman and George E. Dahl, ‘What Will It Take to Fix Benchmarking in Natural Language Understanding?’ (arXiv, 15 October 2021), http://arxiv.org/abs/2104.02145.

[^8]:

     The more intense the AGI racing dynamics, the more different the advanced AI structures across labs (hence differential performance on different benchmarks), the more likely this is an issue. One lab’s racing strategy can be making safety-relevant benchmarks on X to raise salience on X and emphasize its competitive advantage.

[^9]:
     A counterexample is Partnership on AI’s SafeLife, a benchmark for RL agents which receives few submissions and has little influence.

[^10]:

     Modern benchmarks for foundational models are not very expensive and can require only about 1000 examples. A not-so-accurate estimate would be less than a year of time investment for a team of 2-3 researchers, costing about $30,000.  

[^11]:
     Dan Hendrycks et al., ‘Aligning AI With Shared Human Values’, ArXiv:2008.02275 [Cs], 4 March 2021, http://arxiv.org/abs/2008.02275.

[^12]:

     Recent critics point out that ML researchers sometimes interpret benchmark performance in an out-of-context way, presenting the benchmarks as measuring a more general capability that they actually do, given their lack of diversity in task designs and limited scopes. Inioluwa Deborah Raji et al., ‘AI and the Everything in the Whole Wide World Benchmark’ (arXiv, 26 November 2021), http://arxiv.org/abs/2111.15366.

[^13]:

     Douwe Kiela et al., ‘Dynabench: Rethinking Benchmarking in NLP’, in Proceedings of the 2021 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (Proceedings of the 2021 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies, Online: Association for Computational Linguistics, 2021), 4110–24, https://doi.org/10.18653/v1/2021.naacl-main.324Kiela et al.

[^14]:
     Samuel R. Bowman and George E. Dahl, ‘What Will It Take to Fix Benchmarking in Natural Language Understanding?’ (arXiv, 15 October 2021), http://arxiv.org/abs/2104.02145.

[^15]:

      One example may be BIG-bench, a living benchmark of more than 204 language tasks for evaluating language models that encourage new task contributions. Aarohi Srivastava et al., ‘Beyond the Imitation Game: Quantifying and Extrapolating the Capabilities of Language Models’ (arXiv, 10 June 2022), http://arxiv.org/abs/2206.04615.

[^16]:

     Araz Taeihagh and Hazel Si Min Lim, ‘Governing Autonomous Vehicles: Emerging Responses for Safety, Liability, Privacy, Cybersecurity, and Industry Risks’, Transport Reviews 39, no. 1 (2 January 2019): 103–28, https://doi.org/10.1080/01441647.2018.1494640.

[^17]:

     Dan Hendrycks and Mantas Mazeika, ‘X-Risk Analysis for AI Research’ (arXiv, 21 July 2022), http://arxiv.org/abs/2206.05862.

[^18]:
     Defined as “having accurate beliefs about the world.”

[^19]:

     One proposal is AI offense vs. human defense balance, where capabilities of AI count towards both, but differentiably.

[^20]:

     For example, how to carefully hold testing data? How to handle inter-annotator disagreement and ambiguity?

[^21]:

     For a list of problems, see [this](https://forum.effectivealtruism.org/posts/WmrCQTkTgDuk5RhCP/perform-tractable-research-while-avoiding-capabilities#Strategies_for_Tail_Impact) blog post.

[^22]:

     Many academia-lab collaboration originate from academic researchers taking a visiting/internship position at a lab. But this expects to be more difficult.

[^23]:

     For example, the MineRL BASALT competition hosted by NeurIPS 2021 aims to promote research in the area of learning from human feedback. For a paper about a previous year’s competition, see William H. Guss et al., ‘The MineRL 2020 Competition on Sample Efficient Reinforcement Learning Using Human Priors’ (arXiv, 26 January 2021), http://arxiv.org/abs/2101.11071.

[^24]:
     TruthfulQA was used in different ways by different AI labs, thus obstructing comparability of model performance.

[^25]:

     For example, see the [Workshop on Human Evaluation of Generative Models](https://humaneval-workshop.github.io/).

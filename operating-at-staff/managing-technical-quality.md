# 技术质量管理

> 当我可以帮助改进一个意图良好、能够解决实际需求，但是起草它的团队既缺乏经验，也缺乏背景，无法编写一个好的计划来抓住机会的提案时，我感到特别有影响力。在这种情况下，拥有一个结构良好的计划可以帮助大幅度地缩小工作范围，同时还能不损失多少价值，从而更快地发挥影响力。
>
> - Dmitry Petrashko

如果有一件事工程师、工程经理和技术主管可能会达成一致，那就是总是存在技术质量危机。有一种结论很简单直接，那就是: 我们的工程师没有优先考虑质量，我们需要雇佣更好的工程师或重新培训现有的工程师。当然，如果你愿意的话的话，可以随便用“产品经理”或“高管”等代替“工程师”。在一个有冲突的故事里面往往需要有一个明确的反面角色，这样就能很方便地把责任从领导层身上转移了出来。然而，就像大多数把责任甩给权力最小的人身上的做法，既无益又错误。

当你接受低技术质量是由糟糕的决策导致的这一前提时，你就会开始寻找糟糕的判断出现在哪。公司里肯定有人是罪魁祸首。是之前的CTO吗?是那个带着紧张的微笑看着你的总工吗?是每个人都难辞其咎吗?如果这不是那些人的错，会不会是你的错呢?

在大多数情况下，低技术质量并不是危机;这是预期的正常状态。工程师在做质量决策时通常会做出合理的决定，而成功的公司随着时间的推移，随着他们向企业用户扩展、转向或转移高端市场，他们会提高质量标准。在一个运行良好且成功的公司，你之前的大多数技术决策都不会满足你当前的质量门槛。当前技术质量和目标技术质量之间存在差距不是失职，而缩小这个差距即是日常工作，也是有效的工程领导力的重要组成部分。

## 问题根源

作为一个工程领导团队，你的目标是保持适当的技术质量水平，同时把尽可能多的精力投入到核心业务上。您必须在多个时间限制之间平衡质量，而这些时间限制通常有冲突的需求。举个例子，到底是让关键的合作伙伴在下周的截止日期前离开，还是构建一个支持下个季度快10倍发布的平台，你要做的是完全不同的工作。

正如你公司的技术质量标准会随着时间的推移而改变一样，你管理技术质量的方法也会随之演变:

1. 修复那些会立即导致问题的**热点（hot spots）**
2. 采用已知的提高质量的**最佳实践（best practices）**
3. 当代码发生变化时，优先考虑保持质量的**支点（leverage points）**
4. 当组织变动也影响到软件的时候，要匹配**技术向量（technical vectors）**
5. **衡量技术质量**来指导更深入的投资
6. 组建**技术质量团队**，为质量创建系统和工具
7. 运行一个**质控项目**来衡量，跟踪和建立问责制度

当我们深入研究这个方法的工具箱时，请记住选择最便宜、最简单的工具。技术质量是一个长期的游戏。没有所谓的胜利，只有学习和赢得继续玩下去的机会。

## 攀登阶梯

钻研手头的挑战，直到找到一个值得解决的通用问题，这特别有趣。然而，一种同样重要的本能是迅速解决当前的局势，然后转向下一个紧迫的问题。

当您考虑为您的团队和组织做出正确的质量改进时，通常最有效的做法是从最轻量级的解决方案开始。只有当早期的努力在扩展性的压力下崩溃时，才去寻找更重的解决方案。如果您连让团队采用适当的代码风格检测都做不到，那么您想要推出一个全面的高质量程序的尝试就注定会失败。虽然后者在扩展性规模上更有效，但执行起来要困难得多。

所以，先做快速的事情吧!

即使失败了，从简单工作的失败中学习教训要比从困难工作的失败中学教训要快得多。然后您将更快地得到改进的第二次迭代。随着时间的推移，你会转向更全面的方法，但没有必要着急。不要为了在没有适当需要的情况下进行企业规模的协调而放弃早期组织的轻松、快乐和天真。

将这些质量管理阶段呈现为一个向上攀登的线性阶梯很方便，但真正的现实世界中很少这样。更有可能的情况时修复一个热点，推出一个最佳实践，开始进行一个架构review，再舍弃掉那个架构的review，然后又回到热点。如果流程还不成熟就用起来，会带来更多的摩擦而不是价值，而且很快这些不成熟流程就会表现出低效率。如果当前有些流程不管用，先别急着想庆祝取消这个流程，先去试着想办法能不能修好它。

## Hot spots

When confronted by a quality problem, the first instinct is often to identify a process failure that necessarily requires a process solution. If a deployment causes an outage, it’s because the author didn’t correctly follow the code test process, so now we’re going to require tests with every commit – that’ll teach those lazy developers!

There’s the old joke about Sarbannes-Oxley: it doesn’t reduce risk; it just makes it clear who to blame when things go wrong. Unfortunately, that joke applies without humor to how many organizations roll out processes. Accountability has its role, but it’s much more important to understand the problem at hand and try to fix it directly than to create process-driven accountability.

Process rollout requires humans to change how they work, which you shouldn’t undertake lightly. Rather than reaching for process improvement, start by donning the performance engineer’s mindset. Measure the problem at hand, identify where the bulk of the issue occurs, and focus on precisely that area.

The previous example of an untested deploy might benefit from giving direct feedback to the deploying engineer about changing their testing habits. Alternatively, maybe you’re better served by acknowledging that your software design is error-prone and adopting the “define errors out of existence” approach described in A Philosophy of Software Design.

If you have a development velocity problem, it might be optimizing test runtimes, moving your Docker compile step onto a RAM disk, or using the techniques described in Software Design X-Rays to find the specific files to improve.

Systems thinking is the most transformative thinking technique I’ve encountered in my career. Still, at times it can be a siren beckoning you towards fixing a current system you may be better discarding. Sure, you can roll out a new training program to teach your team how to write better tests, but alternatively, maybe you can just delete the one test file where 98% of test failures happen. That’s the unreasonable effectiveness of prioritizing hot spots and why it should be the first technique you use to improve technical quality.

At some point, you’re likely to find that your organization is creating quality problems faster than you’re able to fix hot spots, and that’s when it’s time to move on to adopting best practices.

热点

当遇到质量问题时，第一个本能通常是识别一定需要过程解决方案的过程失败。如果一个部署导致中断，那是因为作者没有正确地遵循代码测试过程，所以现在我们将要求每次提交都进行测试——这将给那些懒惰的开发人员以教训!

关于《萨班斯-奥克斯利法》，有一个老笑话:它不会降低风险;它只是明确了当事情出错时该怪谁。不幸的是，这个笑话没有幽默地适用于多少组织推出流程。问责制有它的作用，但是理解手头的问题并尝试直接修复它比创建过程驱动的问责制重要得多。

流程推出需要人类改变它们的工作方式，这一点您不应该轻易承担。与其追求过程改进，不如从穿上性能工程师的心态开始。测量手头的问题，确定问题的大部分发生在哪里，并精确地关注那个区域。

前面的未测试部署示例可能受益于向部署工程师提供关于改变他们的测试习惯的直接反馈。或者，您最好承认您的软件设计是容易出错的，并采用《软件设计哲学》中描述的“定义存在的错误”方法。

如果您遇到开发速度问题，它可能是优化测试运行时，将Docker编译步骤移到RAM磁盘上，或者使用Software Design x射线中描述的技术来找到需要改进的特定文件。

系统思维是我在职业生涯中遇到的最具变革性的思维方法。尽管如此，有时它可能是一个诱惑你去修复现有系统的警报器，而你可能更好地抛弃它。当然，您可以推出一个新的培训计划来教您的团队如何编写更好的测试，但是，或者，您可以只删除一个测试文件，其中98%的测试失败发生。这就是对热点进行优先排序的不合理效率，以及为什么它应该是你用来提高技术质量的第一项技术。

在某种程度上，您可能会发现您的组织创建质量问题的速度要快于您修复热点的速度，这时就到了采用最佳实践的时候了。

## Best practices

I once worked at a company that didn’t have a team planning process. Over time the head of engineering was increasingly frustrated with the inability to project target dates and mandated that we use Scrum. After the mandate, a manager wrote the Scrum process on a wiki. There was an announcement that we were using Scrum. Managers told their teams to use Scrum. Mission accomplished!

Of course, no one started to use Scrum. Everyone kept doing what they’d done before. It’s awkward to acknowledge mistakes, so the head of engineering declared adoption a major win, and no one had the heart to say differently.

This sad tale mirrors how many companies try to roll out best practices, and it’s one of the reasons why best practices have such a bad reputation. In theory, organizations would benefit from adopting best practices before fixing quality hot spots, but I recommend practices after hot spotting. Adopting best practices requires a level of organizational and leadership maturity that takes some time to develop.

When you’re rolling out a new practice, remember that a good process is evolved rather than mandated. Study how other companies adopt similar practices, document your intended approach, experiment with the practice with a few engaged teams, sand down the rough edges, improve the documentation based on the challenges, and only then roll it out further. A rushed process is a failed process.

Equally important is the idea of limiting concurrent process rollouts. If you try to get teams to adopt multiple new practices simultaneously, you’re fighting for their attention with yourself. It also makes it harder to attribute impact later if you’re considering reverting or modifying one of the new practices. It’s a bit draconian, but I’ve come to believe that you ought to limit yourself to a single best practice rollout at any given time. Channel all your energy towards making one practice a success rather than splitting resources across a handful.

Adopting a single new practice at a time also forces you to think carefully about which to prioritize. Selecting your next process sounds easy, but it’s often unclear which best practices are genuinely best practice and which are just familiar or famous. Genuine best practice has to be supported by research, and the best source of research on this topic is Accelerate.

While all of Accelerate’s recommendations are data-driven and quite good, the handful that I’ve found most helpful to adopt early are version control, trunk-based development, CI/CD, and production observability \(including developers on-call for the systems they write\), and working in small, atomic changes. There are many other practices I’d love to advocate for \(who hasn’t spent a career era advocating for better internal documentation\), but I don’t trust my intuition like I once did.

The transition from fixing hot spots to adopting best practices comes when you’re overwhelmed by too many hot spots to cool. The next transition, from best practices to leverage points, comes when you find yourself wanting to adopt a new best practice before your in-progress best practice is working. Rather than increasing your best practice adoption-in-progress limit, move on to the next tool.

最佳实践

我曾经在一家没有团队计划流程的公司工作过。随着时间的推移，工程主管对无法规划目标日期感到越来越沮丧，并要求我们使用Scrum。授权之后，一名经理在wiki上写了Scrum流程。有个公告说我们正在使用Scrum。经理们告诉他们的团队使用Scrum。任务完成!

当然，没有人开始使用Scrum。每个人都在做他们以前做过的事。承认错误是很尴尬的，所以工程主管宣布采用是一个重大胜利，没有人有勇气说不同的话。

这个悲伤的故事反映了有多少公司试图推出最佳实践，这也是为什么最佳实践有如此坏的名声的原因之一。理论上，组织可以在修复质量热点之前采用最佳实践，但我建议在发现热点之后进行实践。采用最佳实践需要一定程度的组织和领导成熟度，这需要一些时间来开发。

当您推出一个新的实践时，请记住，一个好的过程是演进的，而不是强制的。研究其他公司如何采用类似的做法，记录你想要的方法，在一些参与的团队中进行实践试验，磨去粗糙的边缘，根据挑战改进文档，然后进一步推广。仓促的进程是失败的进程。

同样重要的是限制并发进程的推出。如果你试图让团队同时采用多个新的实践，你就是在和自己争夺他们的注意力。如果您正在考虑恢复或修改某个新实践，那么它也会使您更难在以后确定影响。这有点苛刻，但我已经开始相信，您应该限制自己在任何给定时间的一个最佳实践推出。把你所有的精力都集中在一次成功的练习上，而不是把资源分散在几次练习上。

每次采用一种新的实践还迫使您仔细考虑优先考虑哪一种。选择您的下一个流程听起来很容易，但通常不清楚哪些最佳实践是真正的最佳实践，哪些只是熟悉或著名的。真正的最佳实践必须得到研究的支持，关于这一主题的最佳研究来源是Accelerate。

虽然Accelerate的所有建议都是数据驱动的，而且都非常好，但我发现早期采用的一些最有帮助的建议是版本控制、基于干线的开发、CI/CD和生产可观察性\(包括开发人员对他们所编写的系统的随叫随到\)，以及在小的、原子性的更改中工作。还有许多其他的实践是我想提倡的\(他们没有在职业生涯中提倡更好的内部文档\)，但我不像以前那样相信自己的直觉。

从修复热点到采用最佳实践的转变发生在您被太多需要冷却的热点压垮的时候。下一个过渡，从最佳实践到杠杆点，当你发现自己想采用一个新的最佳实践之前，你正在进行的最佳实践是有效的。而不是增加您的最佳实践采用过程中的限制，继续下一个工具。

## Leverage points

In the Hotspotting section, we talked about using the performance engineer’s mindset to identify the right problems to fix. Optimization works well for the issues you already have, but it’s intentionally inapplicable to the future: the worst sin of performance engineering is applying effort to unproven problems.

However, as you look at how software changes over time, there are a small handful of places where extra investment preserves quality over time, both by preventing gross quality failures and reducing the cost of future quality investments.

I call those quality leverage points, and the three most impactful points are interfaces, stateful systems, and data models.

Interfaces are contracts between systems. Effective interfaces decouple clients from the encapsulated implementation. Durable interfaces expose all the underlying essential complexity and none of the underlying accidental complexity. Delightful interfaces are Eagerly discerning, discerningly eager.

State is the hardest part of any system to change, and that resistance to change makes stateful systems another critical leverage point. State gets complex faster than other systems and has an inertia that makes it relatively expensive to improve later. As you incorporate business obligations around security, privacy, and compliance, changing your stateful systems becomes even more challenging.

Data models are the intersection of the interfaces and state, constraining your stateful system’s capabilities down to what your application considers legal. A good data model is rigid: it only exposes what it genuinely supports and prevents invalid states’ expression. A good data model is tolerant of evolution over time. Effective data models are not even slightly clever.

As you identify these leverage points in your work, take the extra time to approach them deliberately. If it’s an interface, integrate half a dozen clients against the mocked implementation. If it’s a data model, represent half a dozen real scenarios. If it’s stateful, exercise the failure modes, check the consistency behaviors, and establish performance benchmarks resembling your production scenario.

Take everything you’ve learned, and pull it into a technical specification document that you socialize across your team. Gather industry feedback from peers. Even after you begin implementation, listen to reality’s voice and remain open to changes.

One of the hidden powers of investing in leverage points is that you don’t need total organizational alignment to do it. To write a technical vision or roll out a best practice, you need that sort of buy-in, which is why I recommend starting with leverage points. However, if you’ve exhausted the accessible impact from leverage points, it may be time to move on to driving broader organizational alignment.

利用分

在Hotspotting一节中，我们讨论了使用性能工程师的思维来识别需要修复的正确问题。优化对于已经存在的问题很有效，但却有意不适用于未来:性能工程最大的罪恶就是将精力用于未被证实的问题。

然而，当您查看软件是如何随时间变化的时，有一小部分地方的额外投资可以通过防止严重的质量失败和减少未来质量投资的成本来保持质量。

我称这些为质量杠杆点，最具影响力的三个点是接口、有状态系统和数据模型。

接口是系统之间的契约。有效的接口将客户机与封装的实现解耦。持久接口暴露了所有潜在的本质复杂性，而没有暴露任何潜在的偶然复杂性。令人愉悦的界面是敏锐的，敏锐的。

状态是任何系统中最难更改的部分，对更改的抵制使有状态系统成为另一个关键的杠杆点。与其他系统相比，州系统变得更加复杂，并且有一种惯性，使得以后改进它相对昂贵。随着您将有关安全性、隐私和遵从性的业务义务合并在一起，更改有状态系统就变得更加具有挑战性。

数据模型是接口和状态的交集，将有状态系统的功能限制在应用程序认为合法的范围内。好的数据模型是严格的:它只公开它真正支持的内容，并防止无效状态的表达式。一个好的数据模型能够容忍随着时间的推移而发展。有效的数据模型一点也不聪明。

当你在你的工作中确定这些杠杆点时，花额外的时间有意识地去接近它们。如果它是一个接口，那么将6个客户机集成到mock实现中。如果它是一个数据模型，则代表六个真实的场景。如果它是有状态的，则测试故障模式，检查一致性行为，并建立类似于生产场景的性能基准。

将你所学到的所有内容整合到技术规格文件中，以便在整个团队中进行交流。从同行那里收集行业反馈。即使在你开始实施之后，也要倾听现实的声音，对改变保持开放的心态。

在杠杆点上投资的一个隐藏的力量是你不需要完全的组织一致来做它。为了编写技术远景或推出最佳实践，您需要那种买进，这就是为什么我建议从杠杆点开始。然而，如果您已经用尽了杠杆点的可访问性影响，那么可能是时候转向推动更广泛的组织一致性了。

## Technical vectors

Effective organizations marshal the majority of their efforts towards a shared vision. If you plot every technical decision as a vector on a grid, the more those vectors point in the same direction, the more you’ll accomplish over time. Conversely, some of the most impressive engineers I’ve worked with created vectors with an extraordinary magnitude but a misaligned direction. Ultimately those engineers harmed their organizations in their attempts to lead it.

One sure-fire solution to align technical direction is to route all related decisions to the same person with Architect somewhere in their title. This works well but is challenging to scale, and the quality of an architect’s decisions degrade the further they get from doing real work on real code in the real process. On the other extreme, you can allow every team to make independent decisions. But an organization that allows any tool is an organization with uniformly unsupported tooling.

Your fundamental tools for aligning technical vectors are:

* Give direct feedback. When folks run into misalignment, the first answer is often process change, but instead, start with simply giving direct feedback to the individuals who you believe are misaligned. As much as they’re missing your context, you’re missing theirs, and a quick conversation can often prevent years of unnecessary process.
* Refine your engineering strategy from tech spec, to strategy, to vision.
* Encapsulate your approach in your workflows and tooling. Documentation of a clear vision is helpful, but some folks simply won’t study your document. Deliberate tools create workflows that nurture habits far better than training and documentation. For example, provisioning a new service might require going to a website that requires you to add a link to a technical spec for that service. Another approach might be blocking deploys to production if the service doesn’t have an on-call setup established, with someone currently on-call, and that individual must also have their push notifications enabled.
* Train new team members during their onboarding. Changing folks’ habits after they’ve formed is quite challenging, which is frustrating if you’re attempting to get folks to adopt new practices. However, if you get folks pointed in the right direction when they join, then that habit-momentum will work in favor of remaining aligned.
* Use Conway’s Law. Conway’s Law argues that organizations build software that reflects their structure. If your organization is poorly structured, this will lead to tightly coupled or tangled software. However, it’s also a force for quality if your organization’s design is an effective one.
* Curate technology change using architecture reviews, investment strategies, and a structured process for adopting new tools. Most misalignment comes from missing context, and these are the organizational leverage points to inject context into decision-making. Many organizations start here, but it’s the last box of tools that I recommend opening. How can you provide consistent architecture reviews without an articulated vision? Why tell folks your strategy after they’ve designed something rather than in their onboarding process?

Regardless of the approaches you use to align your technical vectors, this is work that tends to happen over months and years. There’s no world where you write the vision document, and the org immediately aligns behind its brilliance. Much more likely is that it gathers dust until you invest in building support.

Most companies can combine the above techniques from hot-spot fixing to vector-alignment into a successful approach for managing technical quality, and hopefully, that’s the case for you. However, many find that they’re not enough and that you move towards heavier approaches. In that case, the first step is, as always, measurement.

技术向量

有效的组织将他们的大部分努力集中在一个共同的愿景上。如果你把每一个技术决策都画成一个矢量，那么这些矢量指向同一个方向的越多，随着时间的推移，你完成的就越多。相反，与我共事过的一些最令人印象深刻的工程师创造出的矢量具有非凡的规模，但却偏离了方向。最终，这些工程师在试图领导组织的过程中伤害了他们的组织。

一个确保技术方向一致的解决方案是将所有相关的决策传递给同一个人和架构师。这可以很好地工作，但是很难扩展，而且架构师的决策质量会随着他们在实际流程中对实际代码进行实际工作而降低。从另一个极端来说，你可以让每个团队都做出独立的决定。但是允许使用任何工具的组织是拥有统一的不受支持的工具的组织。

你对齐技术向量的基本工具是:

提供直接的反馈。当人们遇到偏差时，第一个答案通常是过程改变，但相反，从简单地给你认为是偏差的个人直接反馈开始。就像他们错过了你的语境一样，你也错过了他们的语境，一个简短的对话通常可以避免数年不必要的过程。

从技术规格，到战略，再到愿景，完善你的工程战略。

将您的方法封装到您的工作流和工具中。有一个清晰的愿景的文档是有帮助的，但是有些人就是不会研究你的文档。经过深思熟虑的工具能创造出培养习惯的工作流，这远比培训和文档要好得多。例如，供应一项新服务可能需要访问一个网站，该网站要求您添加到该服务的技术规范的链接。另一种方法可能是，如果服务没有建立随时待命的设置，目前有人随时待命，而这个人也必须启用他们的推送通知，那么就会阻止部署到生产环境。

在新团队成员入职期间进行培训。改变人们已经形成的习惯是相当具有挑战性的，如果你试图让人们接受新的习惯，这是令人沮丧的。然而，如果你让人们在加入时指向正确的方向，那么习惯动力将有利于保持一致。

使用Conway法则。Conway’s Law认为，组织构建反映其结构的软件。如果您的组织结构不好，这将导致紧密耦合或纠结的软件。然而，如果您的组织的设计是有效的，那么它也是提高质量的一种力量。

使用架构评审、投资策略和采用新工具的结构化过程来管理技术变更。大多数不一致来自于缺少上下文，而这些是将上下文注入决策制定的组织杠杆点。许多组织从这里开始，但这是我建议打开的最后一盒工具。您如何在没有明确的远景的情况下提供一致的架构评审?为什么要在他们设计好策略后才告诉他们，而不是在他们刚入职的时候?

不管您使用什么方法来调整您的技术矢量，这都是需要几个月甚至几年才能完成的工作。不存在这样一个世界，即你写下愿景文件，而整个组织马上就能在其辉煌背后达成一致。更有可能的是，直到你投资建立支持，它才会尘埃落定。

大多数公司都可以将上述技术从热点修复到向量对齐结合成一种成功的技术质量管理方法，希望您就是这种情况。然而，许多人发现这些方法还不够，需要使用更重的方法。在这种情况下，第一步总是测量。

## Measure technical quality

The desire to measure in software engineering has generally outpaced our state of measurement. Accelerate identifies metrics to measure velocity, which are powerful for locating process and tooling problems, but these metrics start after the code’s been merged. How do you measure your codebase’s quality such that you can identify gaps, propose a plan of action, and evaluate the impact of your efforts to improve?

There are some process measurements that correlate with effective changes. For example, you could measure the number of files changed in each pull request on the understanding that smaller pull requests are generally higher quality. You could also measure a codebase’s lines of code per file, on the assumption that very large files are generally hard to extend. These could both be quite helpful, and I’d even recommend measuring them, but I think they are at best proxy measurements for code quality.

My experience is that it is possible to usefully measure code quality, and it comes down to developing an extremely precise definition of quality. The more detailed you can get your definition of quality, the more useful it becomes to measure a codebase, and the more instructive it becomes to folks hoping to improve the quality of the area they’re working on. This approach is described in some detail in Building Evolutionary Architectures and Reclaim unreasonable software.

Some representative components to consider including in your quality definition:

* What percentage of the code is statically typed?
* How many files have associated tests?
* What is test coverage within your codebase?
* How narrow are the public interfaces across modules?
* What percentage of files use the preferred HTTP library?
* Do endpoints respond to requests within 500ms after a cold start?
* How many functions have dangerous read-after-write behavior? Or perform unnecessary reads against the primary database instance?
* How many endpoints perform all state mutation within a single transaction?
* How many functions acquire low-granularity locks?
* How many hot files exist which are changed in more than half of pull requests?

You’re welcome to disagree that some of these properties ought to exist in your codebase’s definition of quality: your definition should be specific to your codebase and your needs. The important thing is developing a precise, measurable definition. There will be disagreement in the development of that definition, and you will necessarily change the definition over time.

After you’ve developed the definition, this is an area where instrumentation can be genuinely challenging, and instrumentation is a requirement for useful metrics. Instrumentation complexity is the biggest friction point for adopting these techniques in practice, but if you can push through, you unlock something pretty phenomenal: a real, dynamic quality score that you can track over time and use to create a clarity of alignment in your approach that conceptual alignment cannot.

With quality defined and instrumented, your next step is deciding between investing in a quality team or a quality program. A dedicated team is easy to coordinate and predictable in its bandwidth and is generally the easier place to start.

测量技术质量

在软件工程中度量的愿望通常已经超过了我们的度量状态。Accelerate标识度量速度的指标，这对于定位流程和工具问题非常有用，但是这些指标在代码被合并之后才开始。您如何度量您的代码库的质量，以便您能够识别差距，提出一个行动计划，并评估您努力改进的影响?

有一些与有效变更相关的过程度量。例如，您可以根据较小的拉请求通常质量更高的理解来度量每个拉请求中更改的文件数量。您还可以在假设非常大的文件通常难以扩展的情况下，测量每个文件的代码库的代码行数。这两种方法都很有帮助，我甚至建议对它们进行度量，但我认为它们充其量只是代码质量的代理度量。

我的经验是，有用地度量代码质量是可能的，它归结为开发一个极其精确的质量定义。您对质量的定义越详细，它对度量代码库就越有用，对那些希望提高他们所从事领域的质量的人们就越有指导意义。这种方法在构建演化体系结构和回收不合理的软件中有一些详细的描述。

在您的质量定义中考虑包含一些有代表性的组件:

代码中有多少百分比是静态类型的?

有多少文件有关联的测试?

代码库中的测试覆盖率是多少?

跨模块的公共接口有多窄?

使用首选HTTP库的文件的百分比是多少?

终端是否在冷启动后500ms内响应请求?

有多少函数具有危险的写后读行为?还是对主数据库实例执行不必要的读取?

有多少个端点在一个事务中执行所有的状态突变?

有多少函数获得了低粒度的锁?

在超过一半的pull请求中有多少热文件被更改?

如果您不同意某些属性应该存在于您的代码库的质量定义中:您的定义应该是特定于您的代码库和您的需求的。重要的是要建立一个精确的、可测量的定义。在这个定义的发展过程中会有不同的意见，随着时间的推移，你必然会改变这个定义。

在您开发了定义之后，这是一个度量工具真正具有挑战性的领域，并且度量工具是有用度量工具的需求。仪表的复杂性是最大的摩擦点采用这些技术在实践中,但如果你能通过,你解锁一些相当惊人:一个真正的、动态质量分数随着时间的推移,你可以跟踪和使用在你的方法创建一个清晰的定位,概念不能对齐。

有了质量的定义和工具，您的下一步是决定是投资于一个质量团队还是一个质量计划。一个专门的团队很容易协调，并且在其带宽上是可预测的，而且通常是更容易开始的地方。

## Technical quality team

A technical quality team is a software engineering team dedicated to creating quality in your codebase. You might call this team Developer Productivity, Developer Tools, or Product Infrastructure. In any case, the team’s goal is to create and preserve quality across your company’s software.

This is not what’s sometimes called a quality assurance team. Although both teams make investments into tests, the technical quality team has a broader remit from workflow to build to test to interface design.

When you’re bootstrapping such a team, start with a fixed team size of three to six folks. Having a small team forces you to relentlessly prioritize their roadmap on impact and ensures you’ll maintain focus on the achievable. Over time this team will accumulate systems to maintain that require scaling investment, Jenkins clusters are a common example of this, and you’ll want to size the team as a function of the broader engineering organization. Rules of thumb are tricky here, but maybe one engineer working on developer tooling for every fifteen product engineers, in addition to your infrastructure engineering investment.

It’s rare for these teams to have a product manager, generally one-or-more Staff-plus engineers, and the engineering manager partner to fill that role. Sometimes they employ a Technical Program Manager, but typically that is after they cross into operating a Quality program as described in the next section.

When spinning up and operating one of these teams, some fundamentals of success are:

1. Trust metrics over intuition. You should have a way to measure every project. Quality is a complex system, the sort of place where your intuition can easily deceive you. Similarly, as you become more senior at your company, your experience will no longer reflect most other folks’ experiences. You already know about the rough edges, and you’ll be the first person in line to get help if you find a new one, but most other folks don’t. Metrics keep you honest.
2. Keep your intuition fresh. Code and process change over time, and your intuition is going stale every week you’re away from building product features. Most folks find that team embedding and team rotations are the best way to keep your instincts relevant. Others monitor chat for problems, as well as a healthy schedule of 1:1 discussions with product developers. The best folks do both of those and keep their metrics dashboards handy.
3. Listen to and learn from your users. There is a popular idea of “taste level,” which implies that some folks simply know what good looks like. There is a huge variance in folks who design effective quality investments, but it isn’t an innate skill. The best folks focus on deeply understanding what their users are trying to accomplish and prioritize user needs over implementation constraints. 

   Adoption and usability of your tools are much more important than raw power. A powerful tool that’s difficult to use will get a few power users, but most folks will pass it by. Slow down to get these details right. Hide all the accidental complexity. Watch an engineer try to use your tool for their first time without helping them with it. Improve the gaps. Do that ten more times! If you’re not doing user research on your tools, then you are doomed as a quality investment team.

4. Do fewer things, but do them better. When you’re building for the entire engineering organization, anything you do well will accelerate the overall organization. Anything you do poorly, including something almost great with too many rough edges, will drag everyone down. Although it’s almost always true that doing the few most important things will contribute more than many mediocre projects, this is even more true in cases where you’re trying to roll out tools and workflows to your entire organization \(the organizational process-in-progress limits still apply here!\).
5. Don’t hoard impact. There’s a fundamental tension between centralized quality teams and the teams that they support. It’s often the case that there’s a globally optimal approach preferred by the centralized team, which grates heavily on a subset of teams that work on atypical domains or workloads. One representative example is a company writing its backend servers in JavaScript and not allowing their machine learning engineers to use the Python ecosystem because they don’t want to support two ecosystems. Another case is a company standardized on using REST/HTTP2/JSON for all APIs where a particular team wants to use gRPC instead. There’s no perfect answer here, but it’s important to establish a thoughtful approach that balances the benefits of exploration against the benefits of standardization.

A successful technical quality team using the above approaches will be unquestionably more productive than if the same number of engineers were directly doing product engineering work. Indeed, discounted developer productivity \(in the spirit of discounted cash flow\) is the theoretically correct way to measure such a team’s impact. Only theoretically, because such calculations are mostly an evaluation of your self-confidence.

Even if you’re quite successful, you’ll always have a backlog of high-impact work that you want to take on but don’t have the bandwidth to complete. Organizations don’t make purely rational team resourcing decisions, and you may find that you lack the bandwidth to complete important projects and likewise can’t get approval to hire additional folks onto your team.

It’s a good sign when your team has more available high-impact work than you can take on: if you aren’t selective about which projects to take on, then you’re not thinking broadly enough. This means you shouldn’t necessarily try to grow your technical quality team if you have a backlog. However, if you find that there is critical quality work that you can’t get to, then it may be time to explore starting a quality program.

技术质量团队

技术质量团队是致力于在代码库中创建质量的软件工程团队。您可以将此团队称为开发人员生产力、开发人员工具或产品基础结构。在任何情况下，团队的目标是创建并保持公司软件的质量。

这不是所谓的质量保证团队。尽管两个团队都对测试进行了投资，但技术质量团队有更广泛的职责，从工作流构建到测试，再到接口设计。

当你创建这样一个团队时，从3到6人的固定团队规模开始。拥有一个小团队会迫使你严格地按照影响来排列路线图的优先级，并确保你将注意力集中在可实现的目标上。随着时间的推移，这个团队将积累系统来维护那些需要规模化投资的系统，Jenkins集群就是一个常见的例子，你会希望将团队规模作为更广泛的工程组织的一个功能。这里的经验法则很复杂，但是除了你的基础设施工程投资之外，也许每15个产品工程师中就有一个工程师在开发工具上工作。

这些团队很少有一个产品经理，通常是一个或多个员工和工程师，以及工程经理合伙人来填补这个角色。有时他们会雇佣一个技术计划经理，但通常是在下一节中描述的，在他们进入操作质量计划之后。

当运作这些团队中的一个时，成功的一些基本要素是:

相信指标胜过直觉。你应该有一种方法来衡量每个项目。质量是一个复杂的系统，是那种你的直觉很容易欺骗你的地方。同样地，随着你在公司的职位越来越高，你的经验将不再能反映大多数人的经验。你已经知道困难的地方了，如果你找到了新的，你会是第一个寻求帮助的人，但大多数人不会。指标让你诚实。

保持你的直觉新鲜。随着时间的推移，代码和流程会发生变化，而且你的直觉每周都会变得陈旧，你远离构建产品特性。大多数人发现团队嵌入和团队轮换是保持直觉的最好方法。其他的监控问题的聊天，以及与产品开发人员1:1讨论的健康时间表。最好的人两者都做，并保持他们的指标仪表板在手边。

倾听用户并向他们学习。有一个流行的概念是“品味水平”，这意味着一些人仅仅知道什么是好的。在那些设计有效的高质量投资的人们中存在着巨大的差异，但这并不是天生的技能。最优秀的人员专注于深入理解他们的用户试图完成什么，并将用户需求优先于实现约束。

工具的采用和可用性比原始功能重要得多。一个难以使用的强大工具将获得少数高级用户，但大多数人会忽略它。慢慢来，把这些细节弄清楚。隐藏所有偶然的复杂性。看一个工程师第一次尝试使用你的工具，却没有帮助他们。提高缺口。再做十次!如果你没有对你的工具进行用户研究，那么你注定是一个高质量的投资团队。

做更少的事，但做得更好。当您为整个工程组织构建时，您做得好的任何事情都将加速整个组织。任何你做得不好的事情，包括那些几乎是伟大的、带有太多粗糙边的事情，都会拖累所有人。虽然做一些最重要的事情会比做许多平庸的项目贡献更多，这几乎总是正确的，但当您试图向整个组织推出工具和工作流时更是如此\(在进行中的组织过程限制在这里仍然适用!\)

不要囤积的影响。在集中的质量团队和他们所支持的团队之间存在着一种基本的紧张关系。通常情况下，集中式团队倾向于采用全局最优的方法，这严重影响了在非典型领域或工作负载下工作的团队子集。一个典型的例子是，一家公司用JavaScript编写后端服务器，不允许他们的机器学习工程师使用Python生态系统，因为他们不想支持两个生态系统。另一种情况是，某公司标准化了对所有api使用REST/HTTP2/JSON，而某个团队想要使用gRPC。这里没有完美的答案，但是重要的是要建立一种深思熟虑的方法来平衡探索的好处和标准化的好处。

一个成功的技术质量团队使用上述方法无疑会比同等数量的工程师直接从事产品工程工作的效率更高。事实上，折现的开发人员生产力\(在折现的现金流的精神下\)在理论上是衡量这样一个团队影响的正确方法。这只是理论上的，因为这样的计算主要是对你自信的评估。

即使你非常成功，你也会有一堆你想做却没有时间去完成的重要工作。组织不会做出纯粹理性的团队资源决策，您可能会发现您缺乏完成重要项目的带宽，同样也不能获得批准为您的团队雇用额外的人员。

当你的团队拥有比你所能承担的更多可用的高影响力工作时，这是一个好迹象:如果你没有对承担哪些项目进行选择，那么你的思维就不够广泛。这意味着，如果您有待办事项列表，您不必尝试去发展您的技术质量团队。然而，如果你发现有一些重要的高质量的工作是你做不到的，那么也许是时候开始一个高质量的计划了。

## Quality program

A quality program isn’t computer code at all, but rather an initiative led by a dedicated team to maintain technical quality across an organization. A quality program takes on the broad remit of achieving the organization’s target level of software quality. These are relatively uncommon, but something similar you’ve probably encountered is an incident program responsible for a company’s incident retrospectives and remediations.

The technical components of running a quality program are the sorts of things discussed above, so here we’ll focus on managing a program effectively. Your first step is to find a technical program manager who can co-lead the program and operate its mechanics. While you can make considerable progress on an organizational program’s informational aspects without a technical program manager; however, it’s a trap. You’ll be crushed by the coordination overhead of solo-driving a program in a large organization.

Operating organizational programs is a broad topic about which much has been written, but the core approach is:

1. Identify a program sponsor. You can’t change an organization’s behavior without an empowered sponsor. Organizations behave the way they do because it’s the optimal solution to their current constraints, and you can’t shift those constraints without the advocacy of someone powerful.
2. Generate sustainable, reproducible metrics. It’s common for folks running a program to spend four-plus hours a week maintaining their dataset by hand. This doesn’t work. Your data will have holes in it, you won’t be able to integrate your data with automation in later steps, and you’ll run out of energy to do the work to effect real change; refreshing a metrics dashboard has no inherent value.
3. Identify program goals for every impacted team and a clear path for them to accomplish those goals. Your program has to identify specific goals for each impacted team. For example, reducing test flakiness in their tests or closing incident remediations more quickly. However, it’s essential that you provide the map to success! So many programs demand participation from other teams without providing clear directions on how they can accomplish their part. The program owner is the subject matter expert, don’t offload your strategy to every team to independently reinvent.
4. Build the tools and documentation to support teams towards their goals. Once you’ve identified a clear path for teams to accomplish your program goals, figure out how you can help them make those changes! This might be providing “golden examples” of what things ought to look like, or an example pull request refactoring a challenging section of code into the new pattern. It might be providing a test script to verify the migration worked correctly. It might be auto-generating the conversion commit to test, verify, and merge without having engineers write it themselves. Do as much as you possibly can to avoid every team having to deeply understand the problem space you’re attempting to make progress in.
5. Create a goal dashboard and share it widely. Once you have your program goals communicated to each team, provide dashboards that help them understand their current state, their goal state, and that give reinforcing feedback on their \(hopeful\) progress along the way. The best dashboard is going to be both a scorecard for each team’s work and also provide breadcrumbs for each team on where to focus their next efforts.  

   There are three distinct zoom-levels that your dashboard should support. The fully zoomed-out level helps you evaluate your program’s impact. The fully zoomed-in level helps an individual team understand their remaining work. A third level between the two helps organizational leaders hold their teams accountable \(and supports your program sponsor in making concrete, specific asks to hold those leaders accountable\).

6. Send programmatic nudges for folks behind on their goals. Folks are busy. They won’t always prioritize your program’s goals. Alternatively, they might do an amazing job of making your requested improvements but backtrack later with deprecated practices. Use nudges to direct the attention of teams towards the next work they should take towards your program’s goals. Remember, attention is a scarce resource! If you waste folks’ time with a nudge email or ping, they won’t pay attention to the next one.
7. Periodically review program status with your sponsor. Programs are trying to make progress on an organizational priority that doesn’t naturally align with the teams’ goals. Many teams struggle to break from their local prioritization to accomplish global priorities. This is where it’s essential to review your overall progress with your sponsor and point them towards the teams that prioritize program work. Effectively leveraging your sponsor to bridge misaligned prioritization will be essential to your success.

In a lot of ways, a program is just an endless migration, and the techniques that apply to migrations work for programs as well.

If you get all of those steps right, you’re running a genuinely great program. This might feel like a lot of work, and wow, it is: a lot of programs go wrong. The three leading causes of failed programs are:

1. running it purely from a process perspective and becoming detached from the reality of what you’re trying to accomplish,
2. running it purely from a technical perspective and thinking that you can skip the essential steps of advocating for your goal and listening to the folks you’re trying to motivate,
3. trying to cover both perspectives as a single person–don’t go it alone!

A bad program is a lot like an inefficient non-profit: the goal is right, but few funds reach the intended goal. No matter how you decide to measure technical quality, the most important thing to always remember when running your quality program is that the program isn’t the goal. The goal is to create technical quality. Organizational programs are massive and build so much momentum that inertia propels them forward long after they’ve stopped working. Keep your program lean enough to cancel, and remain self-critical enough to cancel if it ceases driving quality creation.

质量计划

一个高质量的程序根本不是计算机代码，而是由一个专门的团队领导的在整个组织中维持技术质量的计划。质量程序承担了实现组织的软件质量目标级别的广泛职责。这些相对不常见，但您可能遇到过类似的情况，即负责公司事件回顾和纠正的事件程序。

运行一个高质量程序的技术组成部分就是上面讨论的那些事情，所以在这里我们将集中于有效地管理一个程序。你的第一步是找到一个技术项目经理，他可以共同领导这个项目并操作它的机制。虽然在没有技术规划经理的情况下，您可以在组织规划的信息方面取得相当大的进展;然而，这是一个陷阱。你会被一个大型组织中独自驱动一个程序的协调开销压得喘不过气来。

运营组织程序是一个广泛的话题，已经有很多关于它的文章，但核心方法是:

确定计划发起人。如果没有被授权的赞助者，你无法改变一个组织的行为。组织按照他们的方式行事，因为这是他们当前约束的最佳解决方案，如果没有一些有权势的人的支持，你无法改变这些约束。

生成可持续的、可重复的指标。对于运行程序的人来说，每周花4个多小时手工维护他们的数据集是很常见的。这并不工作。你的数据将会有漏洞，你将无法在以后的步骤中将数据与自动化集成起来，并且你将耗尽精力去完成真正的改变;刷新指标仪表板没有内在价值。

为每个受影响的团队确定规划目标，并为他们确定实现这些目标的清晰路径。您的程序必须为每个受影响的团队确定具体的目标。例如，在测试中减少测试薄片或更快地关闭事件纠正。然而，你必须提供通向成功的地图!如此多的项目要求其他团队的参与，却没有为他们如何完成自己的部分提供明确的指导。程序所有者是主题专家，不要把你的策略交给每个团队去独立地重新设计。

构建工具和文档以支持团队实现目标。一旦您为团队确定了实现您的计划目标的清晰路径，请找出您可以如何帮助他们进行这些更改!这可能提供了一个“黄金示例”，说明事情应该是什么样子的，或者一个pull request重构一个具有挑战性的代码段到新模式的示例。它可能提供一个测试脚本来验证迁移是否正确工作。它可能自动生成提交到测试、验证和合并的转换，而不需要工程师自己编写。尽量避免让每个团队都深入了解你想要取得进展的问题所在。

创建一个目标仪表板，并广泛地分享它。一旦你把你的计划目标传达给每个团队，提供仪表板来帮助他们理解他们的当前状态，他们的目标状态，并且在他们前进的道路上给他们\(有希望的\)进展加强的反馈。最好的仪表板既是每个团队工作的计分卡，也是为每个团队提供下一步工作重点的面包屑。

仪表板应该支持三种不同的缩放级别。完全缩小的级别可以帮助您评估程序的影响。完全放大的级别可以帮助单个团队理解他们剩余的工作。这两个层次之间的第三个层次帮助组织领导人让他们的团队负责\(并支持您的计划发起人提出具体的、具体的要求来让这些领导人负责\)。

为那些在目标上落后的人提供有计划的鼓励。人忙。他们不会总是优先考虑你的计划的目标。或者，他们可能会出色地完成您所要求的改进工作，但稍后会使用不赞成的实践返回。使用轻推将团队的注意力引导到他们应该朝向您的计划目标的下一项工作上。记住，注意力是一种稀缺资源!如果你把人们的时间浪费在一封推送邮件上，他们就不会关注下一封。

与您的赞助商定期审查项目状态。程序试图在组织的优先级上取得进展，而该优先级与团队的目标并不自然地一致。许多团队努力打破他们的本地优先级来完成全球优先级。这就是和你的赞助人一起审查你的整体进展的关键所在，并让他们指向优先考虑计划工作的团队。有效地利用你的资助人来弥补不合理的优先顺序对你的成功至关重要。

在很多方面，一个程序就是一个无止境的迁移，适用于迁移的技术也适用于程序。

如果你把所有这些步骤都做对了，你的项目真的很棒。这可能让人觉得工作量很大，哇，确实如此:很多程序都出了问题。程序失败的三个主要原因是:

纯粹从过程的角度运行它，脱离你试图实现的现实，

纯粹从技术角度运行它，认为你可以跳过支持你的目标和倾听你试图激励的人的基本步骤，

作为一个单身的人，试着涵盖这两种观点——不要孤军奋战!

一个糟糕的计划很像一个低效的非营利组织:目标是正确的，但很少有基金能达到预期的目标。无论您决定如何度量技术质量，在运行您的高质量程序时，始终要记住的最重要的事情是程序不是目标。目标是创造技术品质。组织项目是庞大的，并且建立了如此多的动力，以至于在它们停止工作很久之后，惯性会推动它们前进。保持你的程序足够精简，以取消它，并保持足够的自我批评，以取消如果它停止驱动质量创造。

## Start small and add slowly

When you realize your actual technical quality has fallen considerably behind your target technical quality, the natural first reaction is to panic and start rolling out a vast array of techniques and solutions. Dumping all your ingredients into the pot, inevitably, doesn’t work well, and worse, you don’t even know which parts to keep.

If you find yourself struggling with technical quality–and we all do, frequently–then start with something small, and iterate on it until it works. Then add another technique, and iterate on that too. Slowly build towards something that genuinely works, even if it means weathering accusations of not moving fast enough. When it comes to complex systems and interdependencies, moving quickly is just optics. It’s methodical movement that gets the job done.

从小处开始，慢慢加入

当你意识到你的实际技术质量远远落后于你的目标技术质量时，自然的第一反应是恐慌并开始推出大量的技术和解决方案。把所有的食材都倒进锅里，不可避免地，效果不好，更糟糕的是，你甚至不知道哪一部分该保存。

如果你发现自己在纠结于技术质量问题\(我们都经常遇到这种情况\)，那就从一些小的东西开始，反复迭代，直到它奏效。然后添加另一种技术，并对其进行迭代。慢慢地朝着真正有效的方向发展，即使这意味着要经受住对你行动不够快的指责。当涉及到复杂的系统和相互依赖时，快速移动只是光学。只有有条不紊的行动才能完成工作。


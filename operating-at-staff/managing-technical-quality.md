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

## 热点修复

当遇到质量问题时，第一反应通常是找到当前是失败的、需要被妥善解决的流程步骤。如果是因为一个deploy导致宕机，那肯定是因为开发者没有正确地遵循代码测试过程，所以现在我们将要求每次提交都进行测试——这将给那些懒惰的开发人员以教训!

关于[《萨班斯-奥克斯利法（SOX）》](https://zh.wikipedia.org/wiki/%E8%90%A8%E7%8F%AD%E6%96%AF-%E5%A5%A5%E5%85%8B%E6%96%AF%E5%88%A9%E6%B3%95%E6%A1%88)，有一个老笑话:它不会降低风险;它只是明确了当事情出错时该怪谁。只可惜这个笑话里没有提到组织流程。问责制有它的作用，但是理解手头的问题并尝试直接修复它比创建过程驱动的问责制重要得多。

推出一个流程需要人们改变他们的工作方式，这一点您不应该轻易就应诺下来。与其追求过程改进，不如从代入性能工程师的心态开始。测量手头的问题，确定问题的大部分发生在哪里，并精确地关注那个区域。

直接反馈给部署工程师告诉他们应该改变测试习惯可能有助于避免前文提到的未测试就部署的例子。但是更好的处理方式是，承认这个软件设计是容易出错的，并采用[《软件设计哲学》](https://www.amazon.com/Philosophy-Software-Design-John-Ousterhout/dp/1732102201)中描述的“定义存在的错误（define errors out of existence）”方法。

如果您遇到开发速度问题，它可能是优化测试运行时，将Docker编译步骤移到RAM磁盘上，或者使用 [Software Design X-Rays](https://www.amazon.com/Software-Design-X-Rays-Technical-Behavioral-ebook-dp-B07BVRLZ87/dp/B07BVRLZ87/) 中描述的技术来找到需要改进的特定文件。

[系统思维](https://lethain.com/systems-thinking/)是我在职业生涯中遇到的最具变革性的思维方法。尽管如此，有时它可能让你忍不住去修复现有系统，而你其实更应该地克制住这种冲动。当然，您可以推出一个新的培训计划来教您的团队如何编写更好的测试，但是，您也可以删除掉那个一个98%的测试失败发生所在的测试文件。这就是为什么优先处理hot spots的效率高得惊人，以及为什么它（优先处理hot spots）应该是你用来提高技术质量的第一项手段。

在某个阶段，您可能会发现您的组织产生质量问题的速度要快于您修复热点的速度，这时就到了采用最佳实践的时候了。

## 最佳实践

我曾经在一家没有团队计划的公司工作过。随着时间的推移，工程主管对无法规划目标日期感到越来越沮丧，并要求我们使用[Scrum](https://en.wikipedia.org/wiki/Scrum_%28software_development%29)。授权之后，一名经理在wiki上写了Scrum流程。有个公告说我们正在使用Scrum。经理们告诉他们的团队使用Scrum。任务完成! —— 结果是，当然，并没有人开始使用Scrum。每个人都在做他们以前做过的事。承认错误是很尴尬的，最终工程主管宣布采用Scrum是一个重大胜利，没有人有勇气说不同的话。

这个悲伤的故事反映了有多少公司试图推出最佳实践，这也是为什么最佳实践有如此坏的名声的原因之一。理论上，组织可以在修复热点之前采用最佳实践，但我建议在发现热点之后进行实践。采用最佳实践需要一定程度的组织和领导成熟度，这需要一些时间来成长。

当您推出一个新的实践时，请记住，[一个好的流程是渐进的](https://lethain.com/good-process-is-evolved/)，而不是强制的。研究其他公司如何采用类似的做法，记录你想要的方法，在一些参与的团队中进行实践试验，磨去粗糙的边缘，根据挑战改进文档，然后进一步推广。仓促的流程往往是失败的流程。

同样重要的是限制同时进行的流程的数量。如果你试图让团队同时采用多个新的实践，你就是在和自己争夺他们的注意力。如果您正在考虑恢复或修改某个新实践，那么它也会使您更难在以后确定影响。这有点苛刻，但我已经开始相信，您应该限制自己在任何给定时间的一个最佳实践推出。把你所有的精力都集中在一次成功的实践上，而不是把资源分散在几个实践上。

每次只采用一种新的实践还迫使您仔细考虑优先考虑哪一种。选出下一个流程听起来很容易，但通常不清楚哪些最佳实践是真正的最佳实践，哪些只是比较被熟悉或名气大。真正的最佳实践必须得到研究的支持，关于这一主题的最佳研究来源是[Accelerate](https://www.amazon.com/dp/B07B9F83WM/)。

虽然Accelerate的所有建议都是数据驱动的，而且都非常好，但我发现早期采用的一些最有帮助的建议是版本控制、基于主干代码开发、CI/CD和产品的监控\(包括开发人员对他们所编写的系统值班on-call\)，以及在小的、原子性的更改中工作。还有许多其他的实践是我想提倡的\(比如[更好的内部文档](https://increment.com/documentation/why-investing-in-internal-docs-is-worth-it/)\)，但我不像以前那样相信自己的感觉。

从修复热点到采用最佳实践的过渡往往发生在您需要处理热点太多，顾不过来的时候。下一个过渡，从"最佳实践"到"杠杆支点"，发生在当你想采用一个新的最佳实践时，你另外还有最佳实践正在进行。[不要试图同时采用很多最佳实践](https://lethain.com/limiting-wip/)（即不要有太多同时进行的流程），但可以尝试下文提到的杠杆支点这个工具。

## 杠杆支点

在Hotspotting一节中，我们讨论了使用性能工程师的思维来识别需要修复的正确问题。优化对于已经存在的问题很有效，但却不适用于还不存在的问题：性能工程师最大的罪恶就是将精力用于不能被证实的性能问题。

然而，当您查看软件是如何随时间变化的时，一小部分的针对质量的额外投资可以防止未来严重的质量问题和减少未来所需的对质量的投资。

我称这些（一小部分的投资）为杠杆支点，最具影响力的三个点是：接口、有状态系统和数据模型。

_**接口**_是系统之间的契约。有效的接口将client与封装起来的具体实现解耦。持久接口只把最重要最根本的部分展示出来，其他非必要的复杂度则被隐藏。赏心悦目的接口是"[既热情也挑剔](https://increment.com/apis/api-design-for-eager-discering-developers/)"的。

_**状态**_是任何系统中最难更改的部分，这种阻力使有状态系统成为另一个关键的杠杆点。与其他系统相比，状态系统会很快变得非常复杂，并且有一种惯性，使得以后改进它相对昂贵。随着您将有关安全性、隐私和遵从性的业务义务合并在一起，更改有状态系统就变得更加具有挑战性。

_**数据模型**_是接口和状态的交集，将有状态系统的功能限制在应用程序认为合法的范围内。好的数据模型是严格的:它只公开它真正支持的内容，并防止无效状态的表达式。一个好的数据模型能够随着时间的推移而演化。有效的数据模型一点也不需要特别的巧思。

当你在你的工作中确定这些杠杆支点时，花额外的时间有意识地去接近它们。如果它是一个接口，那么先把若干clients集成到mock的实现中试一下。如果它是一个数据模型，则用它描述若干个真实的场景。如果它是有状态的，则测试故障模式，检查行为一致性，并建立类似于生产场景的性能基准。

将你所学到的所有内容整合到技术规格文件中，以便在整个团队中进行交流。从同行那里收集行业反馈。即使在你开始实施之后，也要倾听现实的声音，对改变保持开放的心态。

在杠杆点上投资的一个潜在的效用是你不需要完备的组织来做它。为了编写技术远景或推出最佳实践，您只需要那种口头上表示想要使用的意愿就行，这就是为什么我建议从杠杆点开始。然而，如果您已经用尽了杠杆点的所有可行的影响力，那么可能是时候转向推动更广泛的组织的一致性了。

## 技术向量

有效的组织将他们的大部分努力集中在一个共同的愿景上。如果你把每一个技术决策都画成一个向量，那么这些矢量指向同一个方向的越多，随着时间的推移，你完成的就越多。相反，与我共事过的一些最令人印象深刻的工程师创造出的矢量具有非凡的规模，但却偏离了方向。最终，这些工程师在试图领导组织的过程中伤害了他们的组织。

一个确保技术方向一致的解决方案是将所有相关的决策传递给某个有架构师头衔的人。这可以很好地工作，但是很难扩展，而且架构师的决策质量会随着他们与实际代码的疏远而降低。从另一个极端来说，你可以让每个团队都做出独立的决定。然而，一个公司如果允许使用任何工具，那也就没有任何工具能在这个公司获得普遍的支持。

你align技术向量的基本工具是:

* **提供直接的反馈**。当人们遇到misalignment时，第一个反应通常是改变自己的工作流程。但相反，你应该首先单刀直入地直接给那个你认为和你有misalignment的人沟通。就像他们错过了你的context一样，你也可能错过了他们的context，一个简短的对话通常可以避免数年不必要的工作流程。
* 从[技术规格，到战略，再到愿景](https://yucliu.gitbook.io/staff-engineer/operating-at-staff/writing-engineering-strategy)，**完善你的工程战略。**
* **将您的方法封装到您的工作流程和工具中**。有一个清晰的愿景的文档是有帮助的，但是有些人就是不会研究你的文档。经过深思熟虑的工具能创造出培养习惯的工作流，这远比培训和文档要好得多。例如，供应一项新服务可能需要访问一个网站，该网站要求您添加到该服务的技术规范的链接。另一种方法可能是，如果某个服务没有做到有设置on-call，目前有人on-call，而这个人也必须已经启用他们的推送通知，那么这个服务就会被阻止部署到生产环境。
* **在新团队成员入职期间进行培训**。改变人们已经形成的习惯是相当具有挑战性的，如果你试图让人们接受新的习惯，这是令人沮丧的。然而，如果你让人们在加入时指向正确的方向，那么习惯动力将有利于保持一致。
* **使用Conway法则**。Conway’s Law认为，组织构建反映其结构的软件。如果您的组织结构不好，这将导致紧密耦合或纠结的软件。然而，如果您的组织的设计是有效的，那么它也是提高质量的一种力量。
* 使用[架构评审](https://lethain.com/scaling-consistency/)、[投资策略](https://lethain.com/magnitudes-of-exploration/)和[采用新工具的结构化流程](https://slack.engineering/how-big-technical-changes-happen-at-slack/)来**管理技术变更**。大多数misalignment来自于缺少context，而这些方法是将context注入决策制定的杠杆支点。许多组织是从这一条开始做（align技术向量）的，但这是我建议最后一个尝试的方法。您如何在没有明确的远景的情况下提供一致的架构评审?为什么要在他们设计好策略后才告诉他们，而不是在他们刚入职的时候?

不管您使用什么方法来调整您的技术向量，这都是需要几个月甚至几年才能完成的工作。不存在这样一个世界，即你写下愿景文件，而整个组织马上就能在其辉煌背后达成一致。更有可能的是，直到你投资建立支持性工作，它才会尘埃落定。

大多数公司都可以将上述技术从热点修复到技术向量对齐结合成一种成功的技术质量管理方法，希望您就是这种情况。然而，许多人发现这些方法还不够，需要使用更重的方法。在这种情况下，第一步总是测量。

## 测量技术质量

在软件工程中我们完成的测量工作的往往满足不了我们对测量的需求。《[Accelerate](https://www.amazon.com/dp/B07B9F83WM/)》建立了几个测量速度的指标，这对于找到工作流程和工具中的问题非常有用，但是这些指标都是在代码被合并之后才开始。您如何度量您的代码库的质量，以便您能够识别gaps，提出一个行动计划，并评估您耗费精力所作出的改进的影响?

确实有一些对工作流程的测量是和有效的改变具有相关性的。例如，您可以测量平均每个pull request中更改的文件数目，因为一般而言越小的pull request质量越高。您还可以测量每个文件的代码行数，因为有一般的假设，那就是行数越多越难扩展。这两种方法都很有帮助，我甚至也会推荐测量这些量，但同时我认为它们充其量只是代码质量的间接度量。

我的经验是，有实际效果地测量代码质量是可能的，关键在于需要一套对质量的极其精确的定义。您对质量的定义越详细，它对度量代码库就越有用，对那些希望提高他们所从事领域的质量的人们就越有指导意义。这种方法在[构建演化体系结构（Building Evolutionary Architectures）](https://www.amazon.com/Building-Evolutionary-Architectures-Support-Constant/dp/1491986360/)和[Reclaim unreasonable software](https://lethain.com/reclaim-unreasonable-software/)一些详细的描述。

下面是一些有代表性的质量定义的组成，您可以参考：

* 代码中有多少百分比是静态类型的?
* 有多少文件有关联的测试?
* 代码库中的测试覆盖率是多少?
* 跨模块的公共接口有多窄?
* 使用更好的HTTP库的文件的百分比是多少?
* 终端是否在冷启动后500ms内响应请求?
* 有多少函数具有危险的read-after-write?还是对主数据库执行不必要的读取?
* 在一个transaction中有多少个endpoints改变了所有的状态?
* 有多少函数获得了低粒度的锁?
* 在超过一半的pull请求中有多少hot files被更改?

这里某些定义您可能不认同，这也是非常正常的，因为每个人的质量定义都应该特定于您的代码库和您的需求的。最根本的是要建立一个精确的、可测量的定义。在这个定义的发展过程中会有不同的意见，随着时间的推移，你必然会改变这个定义。

在您确定了定义之后，怎样将这些定义工具化是极具挑战性的，而工具化是收集指标的前提条件。测量工具的复杂度是实际应用的最大阻碍，但如果你能突破这一阻碍，你的收获也会很惊人：一个真正的、动态的随着时间的推移的质量打分，你可以追踪和建立明晰的alignment，这一点一个只有定性的抽象的alignment是做不到的。

有了质量的定义和工具，您的下一步是决定是花精力建立质量团队还是质量流程。一个专门的团队很容易协调，并且在其带宽上是可预测的，而且通常是更容易开始的地方。

## 技术质量团队

技术质量团队是致力于在代码库中实现高质量的软件工程团队。您可以将此团队称为开发人员生产力、开发人员工具或产品基础设施。在任何情况下，团队的目标是创建并保持公司软件的质量。

这不是所谓的质量保证（QA）团队。尽管两个团队都对测试进行了投资，但技术质量团队有更广泛的职责，从工作流构建到测试，再到接口设计。

当你创建这样一个团队时，从3到6人的固定团队规模开始。拥有一个小团队会迫使你严格地按照影响来排列路线图的优先级，并确保你将注意力集中在可实现的目标上。随着时间的推移，这个团队将需要维护越来越多的系统，这也需要更多的投入。Jenkins集群就是一个常见的例子，你会希望[控制团队的规模](https://lethain.com/sizing-engineering-teams/)以适应更广泛的工程师团队。这里没有一个特别通用的经验法则，但是下面这个投入的安排差不多是一个合适的数字：你在基础设施上的投入，加上每15个产品工程师分配一个一个工具开发工程师。

这些团队很少有产品经理，通常是一个或多个Staff+工程师，以及engineering manager合伙人来扮演PM这个角色。有时他们会包括一个技术项目经理，但通常是在他们开始管理质量流程之后（在下一节中描述）。

当运作这些团队中的一个时，成功的一些基本要素是:

1. **相信指标胜过直觉。**你应该有衡量每个项目的指标。质量是一个复杂的系统工程，是那种你的直觉很容易欺骗你的地方。同样地，随着你在公司的职位越来越高，你的经验将不再能反映大多数人的经验。你已经知道困难的地方了，如果你遇到新的困难，你也是第一个寻求帮助的人，但大多数人不具备这样的条件。指标让你更诚实。
2. **保持你的直觉敏锐**。随着时间的推移，代码和流程会发生变化，而且随着你远离开发岗，你的感觉每周都会变得迟钝。大多数人认为团队嵌入和团队轮换是保持直觉的最好方法。其他一些人会追踪聊天记录来发现问题，或者定期地与产品开发人员1对1讨论。当然最好的办法是两者都做，并保持他们的metrics dashboards随时能用。
3. **倾听用户并向他们学习。**有一个流行的概念是“品味水平Taste Level”，意思是有品味水平的人就是知道什么是好的。不同的人怎样去设计有效的质量提升方式有着重大差异，但这并不是说这种品味是什么天生的技能。最优秀的人员专注于深入理解他们的用户试图完成什么，并将用户需求看得比现实的局限更重要。

   工具的采用和可用性比原始功能重要得多。一个难以使用的强大工具将获得少数几个厉害的用户，但大多数人会忽略它。慢慢来，把这些细节弄清楚，隐藏所有[偶然的复杂性accidental complexity](https://en.wikipedia.org/wiki/No_Silver_Bullet)。观察一个工程师在没有任何帮助的情况下是如何第一次尝试使用你的工具。改进gaps。重复以上步骤10次！如果你没有对你的工具进行用户研究，那么你注定是无缘成为一个质量团队的。

4. **做更少的事，但做得更好。**当您为整个工程组织构建时，您做得好的任何事情都将加速整个组织。任何你做得不好的事情，包括那些差一点点就特别优秀的、但是却太粗糙的事情，都会拖累所有人。做少数最重要的事情会比做许多平庸的项目贡献更多，当您试图向整个组织推出工具和工作流时更是如此\(比如很多组织限制progress-in-progress的数量也是同样的原因！\)
5. **不要囤积影响。**在中心化的质量团队和他们所支持的团队之间存在着一种特别的紧张关系。通常情况下，集中式团队倾向于采用全局最优的方法，但这可能会严重影响一些在非典型领域工作的少数团队。一个典型的例子是，一家公司用JavaScript编写后端服务器，不允许他们的机器学习工程师使用Python生态系统，因为他们不想支持两个生态系统。另一种情况是，某公司标准化了对所有api使用REST/HTTP2/JSON，而某个团队想要使用gRPC。这里没有完美的答案，但是重要的是要[建立一种深思熟虑的方法来平衡扩张和标准化的好处](https://lethain.com/magnitudes-of-exploration/)。

一个成功的技术质量团队使用上述方法无疑会比同等数量的工程师直接从事产品工程工作的效率更高。理论上讲，开发人员生产力的折现率\(类似于[现金流折现率](https://en.wikipedia.org/wiki/Discounted_cash_flow)的概念：未来的钱不如现在的钱值钱，未来同样的工作内容做起来比现在做要高效得多\)是可以衡量一个团队影响的。当然，这只是理论上的，因为这样的计算实际工作中基本上只能表示你有多自付。

即使你非常成功，你也会有一堆你想做却没有时间去完成的重要工作。组织不会做出纯粹理性的团队资源决策，您可能会发现您缺乏完成重要项目的资源，同样也不能获得批准为您的团队雇用额外的人员。

当你的团队拥有比你所能承担的更多可用的高影响力工作时，这是一个好迹象:如果你没有对承担哪些项目进行选择，那么你还需要扩展一下思路--如果您还有很多需要做的事情还没做，您就还不必尝试去发展您的技术质量团队；然而，如果你发现有一些重要的质量提升的工作是你做不到的，那么也许是时候开始一个质量计划（quality program）了。

## 质量计划

质量计划中的"计划"（program）不是指的计算机代码（code），而是由一个专门的团队领导的在整个组织中维持技术质量的initiative。质量计划承担了实现组织的软件质量目标级别的广泛职责。这些相对不常见，但您可能遇到过类似的负责公司事件回顾和补救的incident系统。

我们在上面一节已经讨论过运行一个质量计划所需要的组成部分，所以在这一节我们将主要讲解怎样有效地管理一个计划。你的第一步是找到一个技术项目经理，他可以共同领导这个项目。虽然在没有技术规划经理的情况下，您也可以在组织规划方面取得相当大的进展;然而，这是一个陷阱--你最终还是会被大型组织中独自驱动一个程序的协调需要花费的精力压得喘不过气来。

如何运营组织的program是一个[宽泛的话题](https://lethain.com/programs-owning-the-unownable/)，已经有很多关于它的文章，但核心方法是:

1. 找的计划的赞助者sponsor。如果没有有权威的赞助者，你很难改变一个组织的行为。组织按照当下的方式行事，都是因为这是当前限制条件下的最佳解决方案，如果没有一些有权势的人的支持，你无法改变这些限制条件。
2. 生成可持续的、可复现的指标。对于执行计划的人来说，每周花4个多小时手工维护他们的数据集是很常见的--这种方式是不管用的。你的数据将会有漏洞，你将无法在以后的步骤中将数据与自动化集成起来，并且你将耗尽本应去做真正有价值的事情的精力--要知道，不停地去刷新dashboard是没有真正价值的。

为每个受影响的团队确定规划目标，并为他们确定实现这些目标的清晰路径。您的程序必须为每个受影响的团队确定具体的目标。例如，在测试中减少测试薄片或更快地关闭事件纠正。然而，你必须提供通向成功的地图!如此多的项目要求其他团队的参与，却没有为他们如何完成自己的部分提供明确的指导。程序所有者是主题专家，不要把你的策略交给每个团队去独立地重新设计。

构建工具和文档以支持团队实现目标。一旦您为团队确定了实现您的计划目标的清晰路径，请找出您可以如何帮助他们进行这些更改!这可能提供了一个“黄金示例”，说明事情应该是什么样子的，或者一个pull request重构一个具有挑战性的代码段到新模式的示例。它可能提供一个测试脚本来验证迁移是否正确工作。它可能自动生成提交到测试、验证和合并的转换，而不需要工程师自己编写。尽量避免让每个团队都深入了解你想要取得进展的问题所在。

创建一个目标仪表板，并广泛地分享它。一旦你把你的计划目标传达给每个团队，提供仪表板来帮助他们理解他们的当前状态，他们的目标状态，并且在他们前进的道路上给他们\(有希望的\)进展加强的反馈。最好的仪表板既是每个团队工作的计分卡，也是为每个团队提供下一步工作重点的面包屑。

仪表板应该支持三种不同的缩放级别。完全缩小的级别可以帮助您评估程序的影响。完全放大的级别可以帮助单个团队理解他们剩余的工作。这两个层次之间的第三个层次帮助组织领导人让他们的团队负责\(并支持您的计划发起人提出具体的、具体的要求来让这些领导人负责\)。

为那些在目标上落后的人提供有计划的鼓励。人忙。他们不会总是优先考虑你的计划的目标。或者，他们可能会出色地完成您所要求的改进工作，但稍后会使用不赞成的实践返回。使用轻推将团队的注意力引导到他们应该朝向您的计划目标的下一项工作上。记住，注意力是一种稀缺资源!如果你把人们的时间浪费在一封推送邮件上，他们就不会关注下一封。

与您的赞助商定期审查项目状态。程序试图在组织的优先级上取得进展，而该优先级与团队的目标并不自然地一致。许多团队努力打破他们的本地优先级来完成全球优先级。这就是和你的赞助人一起审查你的整体进展的关键所在，并让他们指向优先考虑计划工作的团队。有效地利用你的资助人来弥补不合理的优先顺序对你的成功至关重要。



1. Generate sustainable, reproducible metrics. It’s common for folks running a program to spend four-plus hours a week maintaining their dataset by hand. This doesn’t work. Your data will have holes in it, you won’t be able to integrate your data with automation in later steps, and you’ll run out of energy to do the work to effect real change; refreshing a metrics dashboard has no inherent value.
2. Identify program goals for every impacted team and a clear path for them to accomplish those goals. Your program has to identify specific goals for each impacted team. For example, reducing test flakiness in their tests or closing incident remediations more quickly. However, it’s essential that you provide the map to success! So many programs demand participation from other teams without providing clear directions on how they can accomplish their part. The program owner is the subject matter expert, don’t offload your strategy to every team to independently reinvent.
3. Build the tools and documentation to support teams towards their goals. Once you’ve identified a clear path for teams to accomplish your program goals, figure out how you can help them make those changes! This might be providing “golden examples” of what things ought to look like, or an example pull request refactoring a challenging section of code into the new pattern. It might be providing a test script to verify the migration worked correctly. It might be auto-generating the conversion commit to test, verify, and merge without having engineers write it themselves. Do as much as you possibly can to avoid every team having to deeply understand the problem space you’re attempting to make progress in.
4. Create a goal dashboard and share it widely. Once you have your program goals communicated to each team, provide dashboards that help them understand their current state, their goal state, and that give reinforcing feedback on their \(hopeful\) progress along the way. The best dashboard is going to be both a scorecard for each team’s work and also provide breadcrumbs for each team on where to focus their next efforts.  

   There are three distinct zoom-levels that your dashboard should support. The fully zoomed-out level helps you evaluate your program’s impact. The fully zoomed-in level helps an individual team understand their remaining work. A third level between the two helps organizational leaders hold their teams accountable \(and supports your program sponsor in making concrete, specific asks to hold those leaders accountable\).

5. Send programmatic nudges for folks behind on their goals. Folks are busy. They won’t always prioritize your program’s goals. Alternatively, they might do an amazing job of making your requested improvements but backtrack later with deprecated practices. Use nudges to direct the attention of teams towards the next work they should take towards your program’s goals. Remember, attention is a scarce resource! If you waste folks’ time with a nudge email or ping, they won’t pay attention to the next one.
6. Periodically review program status with your sponsor. Programs are trying to make progress on an organizational priority that doesn’t naturally align with the teams’ goals. Many teams struggle to break from their local prioritization to accomplish global priorities. This is where it’s essential to review your overall progress with your sponsor and point them towards the teams that prioritize program work. Effectively leveraging your sponsor to bridge misaligned prioritization will be essential to your success.

In a lot of ways, a program is just an endless migration, and the techniques that apply to migrations work for programs as well.

If you get all of those steps right, you’re running a genuinely great program. This might feel like a lot of work, and wow, it is: a lot of programs go wrong. The three leading causes of failed programs are:

1. running it purely from a process perspective and becoming detached from the reality of what you’re trying to accomplish,
2. running it purely from a technical perspective and thinking that you can skip the essential steps of advocating for your goal and listening to the folks you’re trying to motivate,
3. trying to cover both perspectives as a single person–don’t go it alone!

A bad program is a lot like an inefficient non-profit: the goal is right, but few funds reach the intended goal. No matter how you decide to measure technical quality, the most important thing to always remember when running your quality program is that the program isn’t the goal. The goal is to create technical quality. Organizational programs are massive and build so much momentum that inertia propels them forward long after they’ve stopped working. Keep your program lean enough to cancel, and remain self-critical enough to cancel if it ceases driving quality creation.



在很多方面，一个程序就是一个无止境的迁移，适用于迁移的技术也适用于程序。

如果你把所有这些步骤都做对了，你的项目真的很棒。这可能让人觉得工作量很大，哇，确实如此:很多程序都出了问题。程序失败的三个主要原因是:

纯粹从过程的角度运行它，脱离你试图实现的现实，

纯粹从技术角度运行它，认为你可以跳过支持你的目标和倾听你试图激励的人的基本步骤，

作为一个单身的人，试着涵盖这两种观点——不要孤军奋战!

一个糟糕的计划很像一个低效的非营利组织:目标是正确的，但很少有基金能达到预期的目标。无论您决定如何度量技术质量，在运行您的高质量程序时，始终要记住的最重要的事情是程序不是目标。目标是创造技术品质。组织项目是庞大的，并且建立了如此多的动力，以至于在它们停止工作很久之后，惯性会推动它们前进。保持你的程序足够精简，以取消它，并保持足够的自我批评，以取消如果它停止驱动质量创造。

## Start small and add slowly

When you realize your actual technical quality has fallen considerably behind your target technical quality, the natural first reaction is to panic and start rolling out a vast array of techniques and solutions. Dumping all your ingredients into the pot, inevitably, doesn’t work well, and worse, you don’t even know which parts to keep.

If you find yourself struggling with technical quality–and we all do, frequently–then start with something small, and iterate on it until it works. Then add another technique, and iterate on that too. Slowly build towards something that genuinely works, even if it means weathering accusations of not moving fast enough. When it comes to complex systems and interdependencies, moving quickly is just optics. It’s methodical movement that gets the job done.

从小处开始，慢慢迭代

当你意识到你的实际技术质量远远落后于你的目标技术质量时，自然的第一反应是恐慌并开始推出大量的技术和解决方案。把所有的食材都倒进锅里，不可避免地，效果不好，更糟糕的是，你甚至不知道哪一部分该保存。

如果你发现自己在纠结于技术质量问题\(我们都经常遇到这种情况\)，那就从一些小的东西开始，反复迭代，直到它奏效。然后添加另一种技术，并对其进行迭代。慢慢地朝着真正有效的方向发展，即使这意味着要经受住对你行动不够快的指责。当涉及到复杂的系统和相互依赖时，快速移动只是光学。只有有条不紊的行动才能完成工作。


---
title: "Switching between B2B and B2C"
permalink: /switching-between-b2b-and-b2c/
date: 2024-09-07
---

I have worked in both setups, and the shift required more recalibration than I expected. 

I spent 5 years building for millions of users at Gojek. Delivery flows, marketplace ordering, three-sided coordination at scale. The feedback loops were fast, the users largely homogeneous and the data was plentiful. Then I joined Snyk, a developer security platform, and almost every instinct I had about product needed adjusting.

The fundamentals still held. Good discovery, clear prioritisation, tight feedback loops. But the environment they operate in is structurally different in B2B, and if you do not recognise that early, you end up applying the wrong muscle at the wrong moment. Here is what I wish I had it mapped out earlier. 

---

# **Economics**

### **The product is shaped by the business model**

In B2B, because deal sizes are large, manually intensive processes can be economically justifiable.At Snyk, we have a professional services team and solution engineers who often write custom onboarding scripts. We also have a dedicated Jump Start programme that helps enterprise customers deploy successfully. Custom work often replaces onboarding features because the unit economics support it.

B2C works very differently. Products are priced per transaction or through subscription tiers. If the product does not work out of the box, users churn within days, and you see it in your metrics almost immediately. That tight feedback loop is valuable, but low individual transaction values also mean every process has to scale without human intervention.

You cannot afford bespoke onboarding. The product has to carry the full weight of adoption itself.

---

# **Discovery**

### **The hardest part is finding the real problem**

In B2C, signals are mostly direct. Customer support tickets, app reviews, and product analytics all come straight from users. They are noisy, but they are close to reality. In B2B, most signals are mediated. They come through account managers, customer success managers, and commercial teams. Each person has already interpreted the original problem through their own lens. By the time feedback reaches Product, it is often a proposed solution rather than the underlying need. Your job is to reverse engineer back to the actual problem.

There is another layer on top of this. The person buying the product is often different from the person using it. For an application security platform, the buying committee might include a CISO or CIO who owns the budget, while the day-to-day users are developers. The buyer wants governance, visibility, and control. The developer wants to ship quickly without interruptions. If you only listen to one side, you will optimise the product in ways that frustrate the other.

Validation also looks very different. In B2C, you can launch a fake door test, collect tens of thousands of data points within hours, and reach statistical significance in days. In B2B, you rarely have enough volume to do that. Your qualitative research has to be significantly stronger because experimentation is often not an option.

Finally, churn is a much slower signal. A customer on a three-year enterprise contract will not disappear overnight. Product issues often surface first in renewal conversations, months before they appear in your dashboards. In B2C, the numbers tell you when something is wrong. In B2B, you have to go looking for it.

The PM implication is that discovery in B2B requires two separate tracks: one for buyers and one for users. Treat feedback from commercial teams as a hypothesis to validate, not a solution to implement.

---

# **Prioritisation**

### **Every roadmap is a series of trade-offs**

Two people ordering food on a delivery app differ along a handful of dimensions: price sensitivity, cuisine preference, and how quickly they want their meal. Two enterprise software customers can differ across industry, compliance requirements, internal tooling, team structure, and security maturity. One customer may need APIs to build internal workflows and granular permissions for hundreds of users. Another simply wants sensible defaults and a smooth rollout. This is why finding your ICP matters so much. The noisiest customers are often the ones your product fits the least. Trying to serve everyone eventually leaves you with a fragmented customer base and a roadmap that serves nobody particularly well.

At the same time, every B2B PM quickly learns that there are really two roadmaps: the one Product planned and the one Sales brings you in real time. That is not dysfunction. It is how enterprise software works. The same applies to escalations. When a large deal is at stake, enterprise sales teams do exactly what they are hired to do: escalate to leadership when Product says no to a customer request. At Snyk, we once built a capability much earlier than planned, and perhaps one we would never have built otherwise, because it helped secure a strategically important enterprise customer. Adoption remained low, but the commercial outcome justified the decision.

Your role as a PM is not to resist these requests. It is to make the trade-offs explicit. *Building this custom API means delaying the Q3 release by six weeks.* Once those trade-offs are visible, leadership owns the decision rather than implicitly handing it back to Product. Know your ICP precisely and build for the customers your product is designed to serve, not simply the ones making the most noise.

---

# **Launch**

### **Shipping the feature is only half the job**

In B2C, you can quietly release a feature to 5% of users, monitor the metrics, and either expand the rollout or pull it back. Marketing usually becomes involved close to launch. In B2B, launches begin much earlier. Before a beta reaches a single customer, sales needs to know how to position it, account managers need to know what to tell existing customers, and marketing needs a story that resonates with both decision-makers and end users. Positioning matters because enterprise buying decisions involve multiple stakeholders with different priorities. Internal enablement is therefore not a nice-to-have. It is part of the product. A feature that is technically live but that nobody in Sales can confidently explain is, in practice, not launched. Legal and compliance also become key stakeholders in ways they rarely do in B2C. This is particularly true in AI, where implementation choices around data storage, processing, and model usage can become contractual blockers rather than technical details.

The implication for a PM is that you need to budget time for internal coordination throughout the rollout, from validation to different phases of availability. Sales enablement, internal documentation, FAQs, positioning are all part of shipping the product.

---

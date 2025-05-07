---
title: "Product Execution Questions"
permalink: /product-execution-questions/
---

Execution interviews are squarely left-brain-type exercises. Can you reason with metrics? Can you think about setting the right KPIs for a product's success and how you will monitor the performance? In general, execution PM questions test your knowledge and comfort with:

- Metrics
- Statistics
- Strategy
- Execution
- Debugging

Execution questions can fall into the following 3 broad categories:

1. North star / Success Metrics
2. Root Cause Analysis (RCA)
3. Tradeoff evaluation 
4. A/B Testing

The north star and RCA type questions are the most common ones and where you should spend 80% of your time practicing these. Let's deep dive into all 4 types of these questions. 

## **Question Type #1:** North Star / **Success Metrics**

Sample questions of this type are:

- What's the most important metric for Airbnb?
- What metrics would you track upon launching a new e-commerce website?

Metrics questions test your ability to reason about and apply metrics. I solved these using the the ["GAME" framework](https://hackernoon.com/metrics-game-framework-5e3dce1be8ac) which is an effective way to think about metrics:

- **G**oal: Define goals for the product. What is our product vision? Where do we see the product growing in the next five years?
- **A**ctions: What actions do we want our users to take that support these goals?
- **M**etrics: Which metrics capture these actions? Tracking these metrics helps indicate if our users are taking the **Actions** that align with our product's **Goals**.
- **E**valuate: What is the one north star metric that the CEO would want to look at for this product (north star metrics are metrics that capture the core value of your product)? How might the other metrics be a false-positive or false-negative? Mentioning the tradeoffs and potential areas of concern with the selected metrics showcases a holistic thinking approach to the interviewers.

**Example: You're the PM of YouTube's Analytics. What would you pick as the three key metrics, and why?**

In this question, let's try to apply the GAME framework that we had mentioned above:

### **Goal**

First, let's define the overall goal for YouTube as a organisation. There are a variety of goals we can select, and they would all be great answers. Overall, YouTube's goal is to provide entertaining and educational video content to users. YouTube also has a subscription plan, called YouTube Red, that charges users a monthly subscription fee to access premium and ad-free content. Some reasonable goals could be: user retention or engagement. In this case, let's select user engagement as the key metric - YouTube wants to see its users getting the most out of the platform.

**Note**: Generally, revenue is NOT a recommended goal. Revenue is usually a byproduct of delivering an incredible and worthwhile user experience. But there could be products which are in the phase where you would want to have monetisation as the goal.  

### **Actions**

So, what user actions align with the goal of user engagement? Here are some to start with:

- Likes on videos
- Watching videos
- Commenting on videos
- Adding videos to playlists
- Creating playlists

All of these are high-level actions that would indicate engagement on the platform. You can go deeper here and think about more actions but they should be relevant to our core goal i.e engaging users on the platform. 

### **Metrics**

The next step is to  define metrics that capture the most important actions from the above. In this case, the most desired user actions could be:

- Watching videos
- Likes on videos
- Commenting on videos

Playlist metrics, while helpful, are a currently niche feature and don't capture the overall health of YouTube as a platform. Clicks and visits are helpful to determine interest, but the other actions (likes, comments, and watches) give a clearer sense that the user enjoyed and engaged with the content. In the end, you need to be able to justify why you chose certain actions. Now, let's re-define the above actions with respect to metrics. It's important to be precise here.

- Average number of likes clicked per user
- Average video watch time per user
- Average number of comments per user

These metrics are defined as averages based on per-user metrics, to give a clear sense of user engagement. **Note:** You could define "Total video watch time for the platform" (Total # of users * Average video watch time per user) too but that will not indicate user level engagement. A high total watch time could just mean a high number of users who are engaged lowly. 

**Evaluate**

We've defined three key metrics that give us a sense of actions consistent with our goal of helping YouTube boost its user engagem ent. Now, let's think of some risks and potential tradeoffs from these metrics to give a complete answer to the interviewer.

- One risk: comments are not necessarily a positive user metric. While commenting users are engaged users, they may be frustrated, offended, or disgusted with the content they are viewing. To mitigate this concern, it'd be helpful to use sentiment analysis tools for comments to check if these comments are generally positive or negative in nature.
- Another risk: watch-time isn't necessarily a positive user metric, when taken to the extreme. Of course, it is beneficial to YouTube to have engaged users on the platform, but many users are nearly addicted to their YouTube viewing habits. If users feel like their time spent on YouTube is a waste, or that they can't help but watch YouTube instead of accomplishing their important life tasks, then perhaps YouTube's attractive influence is actually a downside.

## **Question Type #2: Root Cause Analysis (RCA)**

Sample questions of this type are:

- Facebook is experiencing a 6% decline in user base this month. What could be causing this decline? How would you investigate?
- Usage of Facebook groups is down by 20%. How would you investigate?
- If you were the PM for FB dating app, and the users have dropped by 10%. What would you do?

When an interviewer asks you a RCA question, the first thing is to ascertain what are they looking for. There could be two cases:

1. If the interviewer has an exact root cause in mind, then you should sequentially ask them questions to reach the exact root cause
2. On the other hand, some interviewers won't have an exact root cause in mind but would just want to know your methodology to reach the final root cause. They would want you to cover as much ground as possible and think about all aspects. Hence, the first clarifying question for a RCA question should be to clarify which approach they you prefer you take: 
    1. do you want me to sequentially ask you questions and try to reach the final root cause that you have in your mind? 
    2. Or do I layout my methodology and all aspects I would consider?

**Clarifying questions to start with:** 

- **Trend**: Is it sudden, gradual, seasonal, or recurrent? What is the time duration for the decline?
- **Sanity**: dashboards and source of data maybe incorrect, so we should ensure there are no logging issues (cause could be recent DB migrations etc.).

The methodology can be split into 3 steps: 

1. Explore if we can narrow down the problem by slicing and dicing the data first 
2. factors **internal** to the org
3. factors **external** to the org

**Slice and dice into segments:** 

- Geography
- Platform: mobile vs desktop, device type
- Operating systems on mobile: android vs iOS
- New vs old users

## Internal

**Technical errors:** 

- Server downtime on any APIs?
- Increase in API response times?
- Any crashes on mobile?

**User behaviour on the platform:** 

- **Customer complaints:** support tickets, play store reviews, negative PR on social media?
- **Break down the user flow to check relational metric drop:** In the user flow, are there **other metrics before this** that may have dropped? This helps narrow down where the problem exactly starts. Example: sign-in flow error may lead to fewer videos being watched because that a pre-requisite
- **Break down the product in the context of its usage:** Example: If people have less engagement in Facebook groups, break down groups: public or private groups to deep dive.
- Any additional feature that maybe provides a similar value prop to the end user that's likely **cannibalizing** the existing feature?
    - If the cause is a **new feature launch**, dig into the goal for that feature and see what metrics it positively moved. We need to then see if the overarching goal of the company is being met and if we are ok to make the tradeoff of our metric in question going in the negative direction with the new feature metric going in the positive direction.
- Any business policy-related changes that may affect users to change their mind? (refund policy changes can affect conversion on checkout page)

## External

- **Changes in the competitive landscape**
    - Any new competitors added or wrapped up?
    - Competition launched any campaigns?
- **Any external events**
    - Law / regulation change? (example: repealing of section 230 can lead to less engagement on social platforms)
    - changes to the political environment?
    - holidays?

## Take Action

Once the root cause is known, we will coordinate with the required teams to fix the issue.

- Internal technical: A mobile bug would need a hotfix while a backend issue will need to be fixed by the backend team
- Internal new feature: A new feature might need to be rolled back
- External factor: hard to solve immediately and we would need to see how to tackle it through product development

## Summary

- So in summary, I would:
    - First ascertain if the drop was local to a particular area or global, gradual or sudden.
    - Second, I would look at **internal** and **external** factors to try to see if I can pinpoint the issue.
    - Third, if the issue can be fixed immediately, I would collaborate with the teams to make the necessary change. If not, we should spend some time to understand the issue thoroughly and pickup product changes after that.

## **Question Type #3: Tradeoff Evaluation**

Sample questions:

- Launching "reactions" on facebook posts resulted in 20% reduction in comments while increasing the reacted posts by 30%. How would you evaluate if we should roll this out?
- How do you decide between displaying Facebook's 'People You May Know' feature or an Advertisement in the news feed?
- How would you evaluate a trade-off between boosting ad revenue and decreasing retention?

These questions are meant to evaluate your ability to analyse and reason tradeoffs for a particular scenario which a PM faces on a regular basis in their daily jobs. The tradeoff evaluation questions are not too commonly asked and you can probably practice just a couple of them. There is no fixed framework for answering these but you should look to cover the following in your answer: 

1. What is the product goal and metric associated with both the options 
2. Find a singular common metric that can be used to assess the impact 
3. Consider pros and cons of each option
4. Consider short term and long term aspects 

**Note**: the above parameters are meant to give you a direction to think in and are in no way an exhaustive list of factors to consider. 

**Example: How do you decide between displaying Facebook's 'People You May Know' feature or an Advertisement in the news feed?**

|  | People you may know | Advertisement  |
| --- | --- | --- |
| Goal | **Users:** users will use this feature to discover new friends, add them to their network and eventually have more conversations with them and engage more on the platform 
**Platform:** More engaged users on the platform | **Users**: Through advertisement users will discover products and services relevant to them. Engagement on the platform will decrease if ads are less relevant while it may increase if users find them super helpful and relevant
**Platform:** More revenue earned
**Advertisers:** More products/services sold |
| What does success of the feature depend on? | Users will benefit differently from a "People you may know" feature depending on their existing number of friends. A new user will find the feature extremely useful to find friends while someone who already has a large number of friends may not benefit at all. An ad might be a better option for such users.  | Relevancy of ads plays a huge role in the success of this feature. Relevancy of the ad would depend on the user history and signals that we have which would inturn depend on the activeness of the user of the platform.  |
| Metric | Engagement measured through **time spent on newsfeed/user** | Revenue generated via advertisements measured by **Ad revenue/user** |

If we were to think about rolling these 2 different metrics (time spent and ad revenue/user) into one common metric, we could probably reason that engagement eventually adds to the revenue of the platform and choose revenue as the one common business metric that gets impacted through both features. Afterall more time spent on the platform would eventually mean users are spending more time watching ads and spending on other things (like playing games with friends and making in-game purchases) for the platform to earn revenue. Hence, the common metric could be revenue/user that can be used to compare the 2 features. 

## **Question Type #4: A/B Testing**

Sample questions:

- What are the top 3 types of A/B Experiments you would run on Facebook ads to increase revenue?
- How would you experiment with LinkedIn's homepage to drive sign-in rates?

A/B tests are one of the core tools a product manager can employ for understanding user behavior. In fact, at many large tech companies, product managers are heavily involved with experimentation as a means to validate their product decisions.

[A/B Test Question Guide](A%20B%20Test%20Question%20Guide%20de425db35eec43e0b69cc2beb962ae56.md)

## **Common Errors while answering execution questions**

1. **Not asking questions**
    
    Most PM interview questions are intentionally left undefined. Part of the interview (and part of a PM's job) is to ask the right questions. Show us that you know how to ask important clarifying questions that can really get at what the interviewer is asking. A good approach to ask questions is to think more deeply about the product around the following aspects:
    
    - **Clarify the state of the product:** Is the product in a pre-launch phase? Is the PMF already established and is now in the growth phase? Has it already been scaled and is now in the maturity phase? This information will help better inform the goal for the product given the phase. Generally speaking, focus for pre-launch products would be to get user adoption while a mature product's focus would be on user retention or monetisation.
    
    ![graph of product lifecycle.png](graph_of_product_lifecycle.png)
    
    - **Clarify the positioning of the product with respect to competitors:** Do you understand what the differentiator of the product is and why users use it? This will help you set better informed goals for the product. Example: A dating app like tinder might have a goal to match as many people as possible while a more serious platform like Hinge who claims that their goal is for users to find their long term partner and then delete the app (I am assuming from the tagline "designed to be deleted") would have a different goal like the count of meaningful conversations per user that they can assist.
2. **Trying to get the correct answer**
    
    This applies for both sense and execution questions, but it's an important point to drive home. Most PM interviews don't have a right answer, so stop trying to get the right answer. Instead, focus on the **right process**. Interviewers want to see your critical thinking skills, so be sure to show your work and explain your thought process.
    
3. **Ignoring tradeoffs**
    
    One of the best tactics for PM interview candidates is to **always mention tradeoffs**. By mentioning tradeoffs, you're caveating your answer and directly addressing potential concerns the interviewer may have with your answer. It also indicates that you are thinking holistically about all aspects and possess critical thinking and judgment skills.
    

## Sample Practice Questions

- How would you define success for Instagram stories.
- You are the PM for crisis response, what goal will you set for your team. If an engineer suggested you add a crisis response widget on news feed how would go about making the trade off.
- How would you measure the success of the Instagram story?
- Metrics for 'Save' feature on Fb pages
- Measure success of a Roku stick
- How will you measure success of an app for creating meetings?
- What should the north star metric for Facebook Groups be?

## Relevant Readings:

- Guide to solving RCA type questions

[What to do when your metrics dip](https://productlessons.substack.com/p/what-to-do-when-your-metrics-dip)

- Example interview for RCA

[Product Interview: (Hypothetical) Figma is losing customers at 6-7% weekly. Figure out the reason &](https://medium.com/design-bootcamp/product-interview-rca-solution-design-question-figma-is-losing-customers-at-6-7-weekly-a9c1eb11a236)

- **What is AARRR?** AARRR stands for Acquisition, Activation, Retention, Referral and Revenue and is pretty much the bee's knees when it comes to understanding your customers, their journey and optimizing your funnel as well as setting some valuable and actionable metric goals for your startup.

[AARRR Framework- Metrics That Let Your StartUp Sound Like A Pirate Ship](https://ms-mbalke.medium.com/aarrr-framework-metrics-that-let-your-startup-sound-like-a-pirate-ship-e91d4082994b)

- Tradeoff Evaluation

[How do you decide between displaying Facebook's 'People You May Know' feature or an Advertisement?](https://medium.com/stellarpeers/how-do-you-decide-between-displaying-facebooks-people-you-may-know-feature-or-an-advertisement-f90aaf0ba47e#:~:text=The%20key%20to%20answering%20this,feature's%20impact%20across%20these%20segments)
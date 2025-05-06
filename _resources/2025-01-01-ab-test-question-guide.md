# A/B Test Question Guide

# **How to Answer A/B Test Product Management Questions**

A/B tests are one of the core tools a product manager can employ for understanding user behavior. In fact, at many large tech companies, product managers are heavily involved with experimentation as a means to validate their product decisions. This is why A/B testing-related questions are often asked in a product management interview. For example:

- What experiments would you run on Google's homepage to increase search queries?
- What are the top 3 types of A/B Experiments you would run on Facebook ads to increase revenue?

Of course, there are [simple structures to ace any PM interview](https://hackernoon.com/the-perfect-structure-for-every-product-management-interview-question-3eef80bbfeea), but an excellent experimentation interview answer will be sure to cover a few critical basics. Here's the anatomy of a perfect A/B Test interview answer.

![](https://image.ibb.co/h50eg8/1_Zl0z_Yr_Zatk_Gil1p_IAus_X2_A.png)

## **1. Hypothesis**

First, for any A/B experiment you propose, tell your interviewer what your hypothesis is. What are you actually even testing here? For example, perhaps you believe that by increasing the size of a button, it will increase the clickthrough rate (CTR).

## **2. Methodology**

Now that we have a hypothesis, what exactly are we going to engineer differently to test this hypothesis? For instance, let's run two cohorts of users. In the first cohort, the users will be our control, and will see exactly the same experience as present. In the second cohort, the users will see a button that is increased in area by 50%.

It's important to be precise here. The interviewer needs to understand what exactly is being proposed, and what the experimental setup will look like. A big component of precision in methodology is defining **who** exactly the experiment is being run on. Are we targeting all users on the platform? Or should we pick a proper segment of users for whom we feel this test will be particularly well suited.

> Don't forget to add a control to your experiments — without a control, it's impossible to actually gain useful insights from the data.
> 

## **3. Metrics**

Great, now we have an experimental setup. Next, you need to tell your interviewer what metrics you'll be actually concerned with. What metrics will actually convey useful insights to your product and engineering teams?

In the button example, you'll obviously want to be tracking CTR, but there are a few other metrics that might be relevant and are worth listing:

- Impression count
- CTR on other buttons on the page
- Button hover time
- Time spent on page
- Bounce rate on the button's clickthrough link (assuming the button leads to a new webpage)

To answer these questions, you'll need to understand the goals of the experiment and anticipate potential pitfalls from launching the proposed redesign.

## **4. Impact**

At the end of a day, running an experiment just tells us information. Tell your interviewer how this information will actually be useful. What metrics will you use to make an informed decision about whether or not to launch the proposed feature?

Perhaps you want to ensure that CTR increases with the redesign. Or perhaps the increased clicks on the button shouldn't decrease the overall clicks of buttons on the page.

Ultimately, the answer to this question depends on the specific feature and the goal of the redesign. Here is a great opportunity to relate your answer to the overall vision and goals of the company.

## **5. Tradeoff**

Lastly, every proposed redesign or feature has some sort of tradeoff. What are some potential pitfalls to launching your proposed feature that might not be evident via a purely data-based analysis?

For example, perhaps, by making the button larger, you'll increase the CTR on that button in question at the expense of other elements on the page. Some other great examples of points to make in typical A/B interview questions are qualities like "meaningful interactions" and user delight. These are not easily captured via metrics, and therefore are often missed in an overly quantitative mindset.

# Example**: Improve Google's Homepage**

### **What A/B Tests Would You Run on Google's Mobile Homepage to increase search traffic?**

### **Hints**

Before running any A/B test, define the experiment clearly. Think of A/B tests like science experiments, with a hypothesis, a methodology, and an analysis of how this outcome will tell you information.

In this case, our goal is given to us: we want to increase **search traffic**. This question is phrased in a way that assumes the user has gotten to our homepage. After viewing our homepage, how can we encourage users not to "bounce" away to other sites? One simple example is to make the search box bigger and more noticeable. Can you think of other ideas?

If you're still stuck, think about the perspective of the user. When a user hits the Google homepage, why might they bounce away to a different page? One reason could be that they didn't know how to search for the information they were seeking. Can we make Google's homepage address this user pain point?

### **Our solution**

### **Approach**

A/B test questions fundamentally test your ability to use experimental data to make product decisions. For each proposed experiment, you should list:

- **Hypothesis**: What's your initial guess on an experimental outcome? E.g. Would increasing the button size drive higher click through rates (CTR)?
- **Methodology**: How will you test this hypothesis? E.g. increase the button size for 50% of users for a 50/50 A/B test.
- **Metrics**: What metrics are you concerned with? E.g. CTR on the button.
- **Impact**: How will experimental outcomes affect the product? E.g. we'll decide to make the button bigger if the CTR rate is higher with the bigger button than the smaller button.
- **Tradeoff**: Every A/B Experiment has some sort of tradeoff. What are some potential pitfalls to launching your proposed experiment that might not be evident via a purely data-based analysis? E.g. perhaps making the button bigger drives higher CTR on the button in question, but decreases CTR on other important buttons on the page.

The optimal structure for an A/B PM question can be found [in our A/B question guide](https://www.tryexponent.com/course/lesson/ab-testing). Take a look if you need a refresher.

### **Brainstorm**

Let's start by brainstorming which elements are available to us that we can alter to increase search traffic.

- Google logo
- Search box
- Search button
- Footer
- Profile icon
- Background

This exercise helps us brainstorm what toggles we have to play with, and might spark some ideas.

### **The Experiments**

There are many approaches to this particular question. Below are 3 different experiments, ordered from simple to complex, but there are much more worth considering. Complex answers aren't always better here - the best answers are sophisticated, clearly explained, and high impact.

**1. Make the search box more noticeable**

**Hypothesis** The search box may not be noticeable to users, so we should see if making it more noticeable drives increased engagement. Currently, the mobile google.com home screen is relatively crowded, with several buttons and icons all over the page.

**Methodology** We can accentuate the presence of the search box with a few approaches. Let's focus on making the borders of the search box bolder, slightly coloring the search box, and making the search button thicker and larger. Note that in this interview question, our segment is all users. In other A/B testing questions, proper user segmentation may be necessary.

**Metrics**:

- CTR on search box
- Searches initiated from the search box given an impression
- CTR on other elements of the page
- Bounce rate

**Impact**: Ideally, we'd see an increase in our first two metrics - more clicks on the search box, and more searches initiated from the search box. We'll likely expect to see a decline in other elements on the page, but we want to make sure our bounce rate doesn't substantially increase - this is a sign that our experiment actually just causes users to be more confused at the screen and leave the Google experience entirely.

**Tradeoff**: Even if our experiment is successful and we launch it, it's important to check for qualitative tradeoffs with this feature. For example, we may be discouraging users from using image search. This may not show up as a huge negative loss in our metrics, but it's possible we're funneling users into the search experience and preventing them from noticing other modes of searching. Another tradeoff might be that we're discouraging users from noticing the Google Doodle. The Google Doodle is important branding material for Google's appeal as a creative, educational company. We should observe how this feature may diminish engagement with the Doodle.

**2. Richer zero state queries**

**Hypothesis** Users get to the google.com homepage, but then don't know how to use Google to get the answer they want. For instance, maybe a user doesn't know how to formulate their query.

**Methodology** Let's add a feature that addresses this, by providing "richer" zero-state autosuggest queries when users click on the searchbox. (Zero state refers to the state the search box is in when nothing is typed in it.) The idea here is that users click the search box, then abandon their search since they aren't sure what exactly to type. What if, when users click the searchbox, we show helpful search options. Let's start with something easy: trending search queries at the time (e.g. "Donald Trump Election"). Let's add a new auto-suggest query that shows a trending search result in the top position of the search box, such as in the image below:

![](https://image.ibb.co/bJccUJ/Screen_Shot_2018_07_18_at_9_18_09_PM.png)

**Metrics**:

- % Abandon search query after clicking the search box
- CTR on the new suggested "trending query"
- CTR on the other suggested queries

**Impact**: Ideally, we would notice an increase in clickthrough rate on the new suggested query. We wouldn't want to launch this experiment if we're noticing the CTR on the suggested trending query is significantly lower than the other suggested queries, or if our overall clicks on suggested queries declines. Our principle here is that we want the newly introduced query to produce a net increase in search metrics.

**Tradeoff**: One potential pitfall with launching this feature is the possibility of inappropriate trending query suggestions. Perhaps very violent news is trending, and users may be shocked to see triggering results in their Google search homepage. To mitigate this issue, we should ensure that our safety and abuse algorithms can reliably detect inappropriate content.

**3. Include shortcut links on the homepage**

Note: this proposed experiment is an actual newly launched feature for the Google mobile homepage.

**Hypothesis** When users visit google.com, they aren't sure exactly how to search or how to find some of Google's most useful features. For example, users may never even know that you can search for the weather in Google. What if Google's homepage surfaced useful content categories to users? This might help users discover new features and begin their search queries.

**Methodology** Let's design a series of icons that appear below the search box to show useful features contextually. For instance, we can add a "weather" icon and other useful icons on the homepage. We can update these icons from a set of hundreds of different useful queries (e.g. if the user clicks entertainment, we can surface more entertainment-related queries). An example is shown below:

![](https://image.ibb.co/ivhfGy/wPwkRxp.jpg)

**Metrics**:

- CTR on the various icons
- Search engagement (e.g. abandon rate, number of follow-up queries) given a user clicks the new icons
- CTR on the searchbox

**Impact**: If our searchbox interaction rate declines by a rate greater than the gain from the icons' CTR, then we may not want to launch this feature. Our goal is to increase the user interaction rate on the mobile homepage. Ideally, we'd see a slight decline in the searchbox usage, with a large increase in the new icon CTR, for a net gain in interaction rate.

**Tradeoff**: One potential flaw: users may get comfortable clicking icons instead of typing queries. While normally users search for a variety of queries ("weather tomorrow" "weather in Maine", etc.) users will only search "weather" via the icon click. This could have complex and deleterious effects on long term Google search retention.

Overall, any of these experiments would be great to discuss with a high level of detail and foresight.
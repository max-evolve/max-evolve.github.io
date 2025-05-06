# How many self-driving cars does it take to map the entire continental U.S. in one year?

You’re a Google Maps PM, and the Maps team is just about to launch our new series of Google Street View **self-driving cars**. These Street View cars take panoramic images as they drive along the road, and are completely self-automated — no human needs to be inside! We need to re-map the entire continental US, since our Street View data is now sorely outdated. How many of our new self-driving Street View cars should we purchase to re-map the entire continental US in one year?

Scroll for hints 

**Hints:**

Did you consider that self-driving cars can’t take 360 degree pictures at night?

Did you consider that, although the cars only need to traverse roads once, they’ll still have to re-traverse roads (e.g. dead ends)?

Did you consider the effect of poor weather conditions on driving?

### **Approach**

For this estimation question, let's break the problem down into concrete steps. Generally, we'll want to first understand how many miles of road there exist in the continental US. Then, we can estimate how many cars we need in one year to traverse this mileage, by understanding both the average miles per hour of the car as well as the number of driveable hours in a day. Finally, we'll add in some caveats to our estimate by considering other factors like weather.

### **Driveable miles**

Let’s start by getting a sense of how many driveable miles of road there are in the continental United States. There are a couple approaches here:

- The **Correlation Estimation Strategy**. Try correlating the miles of road with a number you already know. For example, perhaps we can assume that on average, for each car in the US, there is about 0.2 miles of road (since road length and number of cars should be correlated). Then, assume that each US household has one car. Now, we can relate this to a number we should know! (If you don’t know the number of US households, check out [our Estimation Fact Sheet](https://www.tryexponent.com/course/lesson/product-management-estimation)) `100 million * 1 car * 0.2 miles road` = **20 million miles of road**.
- The **Classic Breakdown Strategy**. Try estimating the “road density” of a square mile of the US. There are about 3.5 million square miles of land in the US, which you can estimate based on a rough understanding of how many miles away certain locations are. For instance, if you know that San Francisco to San Jose is about 50 miles, you can guess how many of these distances make up the US both vertically and horizontally, and multiply. Road density is a very rough guess. Break down the problem further into city road density and non-city road density, and estimating the rough land mass of both. We came to 10 miles road / square mile in cities, and 1 mile road / square mile in non-cities, and estimating 100,000 square miles of city and 3.4 million square miles of non-city. This brings our total to `10 miles * 100,000 city square miles + 1 mile * 3.4 million non-city square miles` = **4.4 million miles of road**.

### **Self-driving car speed**

Now that we have a sense of the number of miles in the US, we can estimate how long it will take for a self-driving car to map all the roads. Let’s start with the naive approach, and then add complications and adjustments as needed.

Let’s assume the proportion of residential road to highway road across the entire contintental US is 30% residential and 70% highway road. Then, we can guess that the average self-driving car speed is `30% * 30mph + 70% * 65mph` = **about 55mph**. Now, let’s calculate the amount of time it takes for a car to drive 55mph across all our estimated 5 million miles of road. `5,000,000 miles / 55 mph = 90,000 hours. 90,000 hours / 24 hours in a day = 3750 days / 365 days in a year` = **about 10 years**. We’ve calculated that it will take 10 years for a single self-driving car to map the entire US. If we want to do it in one year, we’ll need a total of 10 self-driving cars.

### **Caveats**

But, we’re not quite done yet. While 10 self-driving cars is a fine answer, it’s an intermediate one, and doesn’t incorporate all the relevant information. Here are some important variables to consider:

**Night time**. The most common interview question error is to assume self-driving cars can map during the nighttime - photographs will be ineffective during this time. Let’s factor that into our analysis, and assume there are only 15 driveable hours per day.

**Dead ends**. Cars won’t simply traverse each road once, since there may be a lot of dead ends in the route. Even if there aren’t dead ends, cars working in tandem may re-trace traversed routes. Let’s factor this into our analysis by including a small percentage increase to the amount of road where this may be the case (e.g. 2%).

**Weather conditions**. Weather conditions like snow, hail, or rain will be severe enough such that the car cannot move or take a clear picture. Let’s assume that about 15 days of the year are inaccessible to the self-driving car.

After all these considerations, there are still even more that are worth mentioning in your interview if you have time. Here are a few:

- Daylight time changes depending on the season. Cars will have more time during the day in summer months than winter months.
- Accidents and maintenance costs. Although the self-driving cars operate smoothly, it’s possible another car may crash into the self-driving car, or that there’s a need for car maintenance. Apply a fudge factor to account for the expected probability of this occurrence.
- Gas stops. Factor in refueling time based on an estimate of the car’s MPG.

### **Final solution**

Here’s our final equation, factoring in the analysis above. We use the 4.4 million mile road estimate based on the road density strategy, and assume 55mph for the average speed of the car.

`5,000,000 miles * 102% (for dead ends) / 55mph` = **92,000 hours**. `92,000 hours / 15 driveable hours in a day = about 6000 days / 350 driveable days in a year` = **17 years**. This means, to map the entire continental US in one year, we’ll need **17 self-driving cars**.
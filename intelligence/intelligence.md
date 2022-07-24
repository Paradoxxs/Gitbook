---
description: Ground work intelligence analysis
---

Intelligence is the collection, analysis and exploitation of information in support of an specific object.


## Counterintelligence

The purpose of counterintelligence is to identify, assess, neutralize and exploitation.\
The intelligence activities of an adversary.

## Intelligence level

Tactical

* Specific action that can be taken to defend the organization.

Operational

* Bridges tactical and strategic, by assessing the organization operating environment to identify potential risk.

Strategic

* Define the objectives and guidance on what threats should be mitigated and the security posture of the organization.

## Intelligence classification

** Unknown-unknown**

Unaware of the existence of a threat

**Known-unlnown**

The threat is known but not understood

**Known-known**

We both know and understand the threat, and resource to put in place to mitigate them.


# Intelligence process life cycle

![](https://upload.wikimedia.org/wikipedia/commons/thumb/5/58/The_Intelligence_Process_JP_2-0.png/350px-The_Intelligence_Process_JP_2-0.png)

## Direction

Understanding the needs of the audience, and define intelligence requirements to address the threat relevant to the organization.

## Collection

Gathering of data from different source. This is mostly an automated process, this is mostly because there to much information to be collected manual.\
This is specially true when it comes to the internal system.

Data in a vacuum, without context, is difficult to interpret and understand, which is why we have multiple sources of data that can be correlated together to create intelligence, by enriching data with context. Providing value by passing the information to the different stakeholders.


### Collection management framework

Collection management framework is an data sheet that explain the different source of information.\
what we can expect from them.\
and the question they can help us answer.\
More importantly identify if you are missing any sources of information.&#x20;

-WIP- create collection management framework table



## Processing & exploitation

This stage involves the translation of the raw data into an format that either human understandable format or common computer format for injection.\
Another part of this stage is the evaluation on the relevance and reliability of the data collected.


### Rosetta stone

Translation naming schema what the different vendors calls malware, threat actors, etc.. Very helpful to understand different threat reports.

## Analysis

Combining separate pieces of information to identify patterns within the data.\
Then interprets what the significance of the new knowledge.

![](https://upload.wikimedia.org/wikipedia/commons/e/ee/Relationship_of_data%2C_information_and_intelligence.png)


### Bias

Everyone has bias, it the human brain trying to simplify information around us.
it important for an analyst to be aware of their own bias, allowing you to counter your biases the effect on your analysis.

Which is why the intel team, need to be compromised of multiple different type of people, with difference experience and backgrounds to combat their biases.

Cognitive bias [24 Cognitive Biases stuffing up your thinking](https://yourbias.is/)

### Structured analytic techniques (SAT)

* Decision matrix
* Decision trees

### Data pivoting / Analytic leaps

1. Start with single indicator
2. Pivot through each data source and add relevant data points
3. Validate, ensure links contain context and ensure the links are meaningful
4. Identify the relevant indicators
5. Be aware of the Kevin bacon effect
   * It takes 6 hops/pivoting to know anyone in the world.

## Dissemination

Distribution of the intelligence report, It important that the report is delivered in such away that the consumer can understand it and apply it to their need.




### Estimative language

Because the meaning of words like: likely, might happen, etc.\
Is highly subjectively, which is why it is important to have an agreed-upon language of the estimate, like a scale.

|Word|estimate|variable|
|---|---|---|
|Certain	|100%|Give or take 0%|
|Almost Certain|93%|Give or take about 6%|
|Probable	|75%|Give or take about 12%|
|Chances About Even|50%|Give or take about 10%|
|Probably Not	|30%|Give or take about 10%|
|Almost Certainly Not|7%|Give or take about 5%|
|Impossible|0|Give or take 0%|


Another good idea is to add percentages to make the meaning clear. e.g. might happen (70%)

## Feedback

Feedback loop for improving the process.





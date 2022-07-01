---
description: Taking intelligence and applying it to cyber
---

# Cyber treat intelligence

## Threat hunting

Is the active process of trying to find signs of compromise.

### Intel to threat hunting and incident response

1. Threat model
   * Select a threat and its tactics techniques and procedures (TTP)
2. Create a hypothesis
   * Create a testable statement related to how the threat TTP would impact your organisation
3. Overlay the tradecraft and your CMF
   * Map the hypothesis to the CMF to identify what needed to be tested
4. Hunting
   * Hunt aginst the hypothesis and CMF
5. Learn
   * Identify gaps and opportunities of improvement
   * Create playbooks for future investigation against the TTP in your environment



## Pyramid of pain

The higher up in the pyramid of pain, the more difficult will it will for the threat actor to change their behaviour.

![](https://remnote-user-data.s3.amazonaws.com/g5p1PSh-1o05NUSgQmhouqlrwO9f18sqF-tml3DI0VwG9TkkqWk7Xzm6BGO3EDTf13uRFDTLFHUOpy8Smhhakct4i4OtYx\_l9ZEd6GexLn0tGt75mY\_L2hRbLe7R\_SfI.png)

## Threat feeds

It important to understand threat feeds are not intelligence, they are data feeds, and often without context why the data is in the feed. \
It up to the analysis to take the data and use it an assessment.&#x20;

Before acquiring an threat feed you need to understand why you need it, and how it relates to you.\
It important to be critical when selecting threat feeds, one of the first question to ask before acquiring is to ask about the source of the information. \
E.g if you are an company operating in Europe and the feed is from company in asia. The data might not be relevant to you.

Good way to start with threat feed is using open source like DShield, if you do not know how to handle it, you are not ready for the next level. One of the key question to ask about threat feed is the data source of the feed.



## Tool collection

[GitHub - IVMachiavelli/awesome-threat-intelligence: A curated list of Awesome Threat Intelligence resources](https://github.com/IVMachiavelli/awesome-threat-intelligence)

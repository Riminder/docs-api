# Talentsoft

**Talentsoft** is an European leader in talent management, it is a cloud-based solution improving employees' professional growth at the heart of company's HR processes.

In this overview we'll explain the general flow of the integration between HrFlow.ai and Talentsoft. You'll learn about the different features that this integration can offer.

![](../../../.gitbook/assets/image%20%2816%29.png)

## Integration's flow :

The integration between a TalentSoft user and HrFlow exists as part of a flow, a continuum of events that gets something done.

This interactive flow can be simplified to three basic steps:

* Authentication
* Indexation \(Profile / Job\)
* Scoring API / Reasoning API

## 1\) Authentication :

Enabling HrFlow in Talentsoft, you’ll be able to immediately either score your candidates for a given offer or score your offer for a given candidate.

But, before assisting to magic show the integration has to start somewhere, with a knock on the door to request entry.  
  
Once you have your **Client Id / Client Secret / Client URL** , you will be able to create in your HrFlow workspace , a Talentsoft source / board , so HrFlow could index automatically existing profile / job.

![](../../../.gitbook/assets/image%20%286%29.png)

## 2\) Indexation :

By creating a Talentsoft Source / Board, and successfully authenticated, HrFlow will automatically pull and index all existing profiles / Jobs.

Our pulling system will incrementally send profiles / jobs to HrFlow Platform , in interval range of 5 minutes between every pull action.

## 3\) Scoring and Reasoning :

![](../../../.gitbook/assets/image%20%2813%29.png)

### 3.1 Filters :

![](../../../.gitbook/assets/image%20%2811%29.png)

Filters aim to refine recruiter's search based on location, experience duration Reasoning Criteria are not mandatory , it comes as complementary information to highlight the reasons behind every match. ... 

### 3.2 Applied / Suggested Criteria :

![](../../../.gitbook/assets/image%20%2810%29.png)

Criteria let recruiters to enhance the quality of their search experience and to help them getting insights about scoring results.

Initially HrFlow.ai did not apply any pre filter on the set of profiles / jobs.  
Instead, there is suggested tags that could by applied in order to refine recruiter's search.

HrFlow.ai consider 2 kinds of criteria: 

* Boolean Criteria,
* Reasoning Criteria

Boolean criteria are basically the extracted skills after parsing a profile / job, while applying a boolean criteria, our search engine will send all profile / job that contains this criteria or a similar word \(.ie e-commerce / commerce / commercial ...\).



{% hint style="info" %}
Same **process** is applied in both Matching Profiles and Jobs.
{% endhint %}

### 3.3 Matching Criteria

![](../../../.gitbook/assets/image%20%2815%29.png)

To enhance recruiter experience, all applied criteria **should** appear in the matching profiles / jobs, so  recruiters could easily process their search without trying infinite possible combination to get what they are searching for.

So profile / job will show up if they contain at least one of applied criteria.

Additional information are added in complementary information section, in the case of matching candidate HrFlow enrich Profile by its interests.

### 3.4 Scores :

![](../../../.gitbook/assets/image%20%289%29.png)

Profiles / Jobs scores are already calculated using [Scoring API](https://www.hrflow.ai/scoring.html), and in order to highlight the reasons behind every match and list the matching criteria we need to appeal [Reasoning API](https://www.hrflow.ai/reasoning.html).



##   


---
title: "All My Commits To Prod"
outputs: ["Reveal"]
description: "Presentation about practices"
reveal_hugo:
    custom_theme: "reveal-hugo/themes/robot-lung.css"
    margin: 0.2
    highlight_theme: "color-brewer"
    transition: "slide"
---

# Achieving Delivery Acceleration
### why I do all in Prod

<small>Created by [Alvaro](https://kanekotic.xom) ([@kanekotic](https://twitter.com/kanekotic)) @[ClimatePartner](https://www.climatepartner.com).
</small>

---

# Am I crazy?!

<img src="/images/crazyvswise.png" width="500"/>

---

{{% section %}}

# Why?

<img src="/images/why.jpg" width="700"/>

---

### Team & Organizational Performance

<img src="/images/accelerate.jpg" width="320"/>

{{% note %}}
- Accelerate a great book that is extract of the state of devops report
- It does not just speak about Technology but also about organization and culture
- Read it
{{% /note %}}

---

### 4 key metrics: 2017

<img src="/images/key_metrics.png" width="550"/>

{{% note %}}
- This are metrics that have help correlate high performance teams
- They are based on trying to measure speed and stability
{{% /note %}}

---

### 4 key metrics: Word of caution

<img src="/images/metrics_caution.png" width="335"/>

{{% note %}}
- Not a one size fit all solution.
- Useful for continuous improvement, No reporting.
- As all metrics they can be abused by management
- The solution and practices are not always the same for all teams
{{% /note %}}

{{% /section %}}

---

# Achieving Speed

<img src="/images/full_speed.jpg" width="700"/>

---

{{% section %}}

# Attitude

<img src="/images/positive_attitude.jpg" width="400"/>

--- 

### You Build it you Run it

Create DevOps Culture. Not a Dev vs Ops.

<img src="/images/run_it.jpg" width="400"/>


🟢 All Metrics

{{% note %}}
- Mention Normally developers are ask for delivery speed, and operations counterpart stability.
- Devops culture is based on collaboration on running everything as a team of developers that at the same time observe operations.
- Ops need to become a tool creator for teams, and not run their operations.
{{% /note %}}

--- 

### Be a Boy Scout

Don't continue the same path if you think something can be done better.

<img src="/images/scout.jpeg" width="300"/>

🟢 All Metrics

{{% note %}}
- If you see code that can be done better, or some practices that can help delivery don't shy away because you are currently not doing it
- If you don't do it nobody will
{{% /note %}}

--- 

### Learn to adapt

Not all problems need the same tool.

<img src="/images/buddhist.jpg" width="400"/>

🟢 All Metrics

{{% note %}}
- Not all problems are solve the same so find your tools
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# Observability

<img src="/images/no_alarms.png" width="700"/>

--- 

### Alarms

- Get notified when something happens
- Ex. Datadog + Pager Duty

🟢 MTTR

{{% note %}}
- Alarms allow you to be lazy. you don't need to jump or spend time and brain power if its not required.
{{% /note %}}

--- 

### Metrics Dashboards

- Visualization
- Ex. Datadog

🟢 MTTR

{{% note %}}
- When something happens dashboard can gide you to where might the problem be.
- You need to learn how to read them and there are multiple types.
{{% /note %}}

--- 

### Metrics Dashboards
Details & Status

<img src="/images/dashboards.jpeg" width="1000"/>

🟢 MTTR

{{% note %}}
- It is easy to spot where the problem is in a status dashboard. 
- Root Cause is we don't enter a cognitive overload state like with the details.
{{% /note %}}

--- 

### Logs

- To go in depth in issues.
- Do not log everything.
- Ex. Kibana

🟢 MTTR

{{% note %}}
- This is the lower level you want to go. It should tell you where in the code is your issue.
- Do not log everything, just what will help you fix things. It can complicate finding what is happening if you have tons of logs.
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# Deployment

<img src="/images/deploy_prod.jpg" width="300"/>

--- 

### Continuous Integration, Delivery & Deployment

<img src="/images/continuous.png" width="1000" style="background-color:white;" />

🟢 Deployment Frequency
🟢 Lead Time For Changes
🟢 MTTR

{{% note %}}
- This are steps in a journey.
- Continuous integration: It allows you to make sure you reproduce what you can do local somewhere else.
- Continuous Delivery: Now that you reproduce things get them somewhere that can be tested.
- Continuous Deployment: Deliver to your clients and not only to your team.
- The more mature a team is in the journey the more confident they are of going the next definition
{{% /note %}}

---

### Everything as code

<img src="/images/infra_as_code.jpg" width="700"/>

🟢 Lead Time For Changes
🟢 MTTR

{{% note %}}
- This helps to become a devops team and not just a devs and ops segmented group.
- If you control all the parts you are building the capabilities into the solution. If not you are wrapping around things that might not fit.
- It affects both stability and speed. Your infrastructure follows your code, and vice versa.
{{% /note %}}

---

### Blue/Green Deployment

<img src="/images/blue_green.jpeg" width="1000"/>

🟢 Change Failure Rate

{{% note %}}
- Blue green is not just a tool to minimize downtime, it can also be used as a tool to minimize failure rate.
{{% /note %}}

--- 

### Canary Release 

<img src="/images/canary.jpeg" width="1000" />

🟢 Change Failure Rate

{{% note %}}
- Helps Minimize the risk of new features braking things.
- Canary releases come from miners practices. If the canary dies the human might also die.
- It gives you control at infrastructure level and is highly tide to your release capabilities.
- you can probably have issues with multiple canaries with different combination of features. 
{{% /note %}}

--- 

### Feature Toggles

<img src="/images/toggles.jpeg" width="1000" />

🟢 Change Failure Rate
🟢 MTTR
🟢 Lead Time For Changes


{{% note %}}
- The intention is similar to canary releases. Helps Minimize the risk of new features braking things.
- It gives you control at code level. 
- 2 types: release (on/off), context (Higher level of granularity user Ids, location, disk space...)
- Allows you to disconnect from the release cycle. So you can react faster.
- Enables other capabilities like A/B testing, and testing in prod.
{{% /note %}}

---

### Environments

<img src="/images/environments.jpeg" width="1000" />

🟡 Change Failure Rate
🟡 Lead Time For Changes

{{% note %}}
- Adds 'safeguards' and places to test that are different than the users environment.
- They are difficult to maintain and align between different teams, it can lead to strange behavior.
- Difficult to validate the end result.
- They have a dollar cost attached.
- Normally to solve an issue you need to go through all the environments, affecting the time to get solutions out.
{{% /note %}}

---

### Single Environment

<img src="/images/single_environment.jpeg" width="500" />

🟢 MTTR
🟢 Lead Time For Changes

{{% note %}}
- It allows you to control what data is for test.
- A single environment ensures continues alignment.
- Smaller $ cost.
- You get the real performance & behavior.
- Achieve this is to have a flag across your system
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# Testing

<img src="/images/testing.jpg" width="500" />

--- 

### Pyramid

<img src="/images/pyramid.jpeg" width="700" />

🟢 Change Failure Rate

{{% note %}}
- Probably the most important of all.
- Tests are not just manual or unit. There are tons of things that need to be validated.
- All validations should be reproducible.
- This is the main thing that brings stability as it brings quality into the codebase
{{% /note %}}

---

### Validate in Production

- Get real behaviors of interactions
- Get real performance

🟢 Change Failure Rate

{{% /section %}}

---

{{% section %}}

# Source Code

<img src="/images/merge_branch.jpg" width="500" />

---

### Git Flow & Trunk Base

<img src="/images/trunk.png" width="700" />

🟢 Deployment Frequency

{{% note %}}
- Long lived branches are difficult to merge.
- When you merge sometimes you need to revalidate all the work.
- On only branch force you to think about small units. 
- You get the entire picture of your code all the time.
- There are minimal merge conflicts.
- I am not doing toggles can I do trunk based development. There are other ways like abstractions that are not connected that achieve the same goal.
{{% /note %}}

---

### Versionless: Expand & Contract

<img src="/images/expand_contract.jpeg" width="700" />

🟢 Lead Time for Changes


{{% note %}}
- Software evolves continuously, so things will get deprecated and be replaced all the time.
- Versions allow you to separate changes. But the more versions the more complex the maintenance and more costly.
- Expand an contract allows you to do parallel changes. 
- keep compatibility till nobody uses it.
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# Are you at full speed?

---

<img src="/images/laugh.jpg" width="300" />

 hell no! This will always be a moving target
 
 Practices always change

{{% /section %}}

---

<img src="/images/questions.jpg" width="500" />

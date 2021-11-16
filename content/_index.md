---
title: "Is not a Monolith Anymore! But is not enought!"
outputs: ["Reveal"]
description: "Presentation about practices"
reveal_hugo:
    custom_theme: "reveal-hugo/themes/robot-lung.css"
    margin: 0.2
    highlight_theme: "color-brewer"
    transition: "slide"
---

# Is not a Monolith Anymore!
## #IsNotEnought

<small>Created by [Alvaro](https://kanekotic.xom) ([@kanekotic](https://twitter.com/kanekotic)) @[ClimatePartner](https://www.climatepartner.com).
</small>

---

{{% section %}}

# The history

---

# The monolith
### Why we hate it?

<img src="/images/monolith.png" width="500"/>

{{% note %}}
- There was a time we all have to work on the same code base
- You release a big thing and pray it works
- You go through big cicles of validating the entire thing
- You need big teams only to validate, it makes the release cicle bigger
{{% /note %}}

---

# The microservice
### Why we love it?

<img src="/images/microservice.png" width="500"/>


{{% note %}}
- we love the concept because it means work in smaller things
- we can break less stuff so it gives us more confidence
- we denpend on less people to achieve what we want
{{% /note %}}

{{% /section %}}

---

# Awesome!
### Presentation finish!!!

---

# or is it not finish...

---

{{% section %}}

### Can there be problems with microservices architecture?

---

# Did you had any of this cases?
- Before we release a new version we need to sync deploys with another team.
- Our application was down but is not our issue.
- We deploy at 10 pm because is when nobody is online.
- ...

---

### Dam You Microliths!

<img src="/images/microliths.jpg" width="700"/>

{{% note %}}
- when you have syncronous calls to other service you are not decoupled from them
- There is even cascading possible without your knowledge
- your boundaries are not defined
{{% /note %}}

---

# efectively you have a monolith broken into pieces

{{% /section %}}

---

# We are doomed!!!

<img src="/images/timetopanic.jpg" width="700"/>

---

# Any Alternative?!

---

{{% section %}}

# The Naive Solution
### circuit braked Microliths

<img src="/images/greenlantern.png" width="500"/>

{{% /section %}}

---

{{% section %}}

# A Better Solution
### Reactive Microliths

<img src="/images/reactivehero.jpeg" width="700"/>

##### wait still microliths?!

---

## Baby steps

- Use Pub/Sub (ex. kafka, kinesis)
- Send the same domain object in a message

<img src="/images/reactivemicroliths.jpg" width="700"/>

{{% note %}}
- 
{{% /note %}}

{{% /section %}}

---

{{% section %}}

# The Best Solution: Reactive Microsystems

{{% /section %}}

---

# Questions?

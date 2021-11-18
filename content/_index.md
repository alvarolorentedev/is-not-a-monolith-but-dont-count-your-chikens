---
title: "Is not a Monolith Anymore! But is not enough!"
outputs: ["Reveal"]
description: "Presentation about the different ways of doing microservice"
reveal_hugo:
    custom_theme: "reveal-hugo/themes/robot-lung.css"
    margin: 0.2
    highlight_theme: "color-brewer"
    transition: "slide"
---

## 🥂 You don't have a Monolith Anymore 🥂
##### 😱 But it behaves like one 😱

<small>Created by [Alvaro](https://kanekotic.xom) ([@kanekotic](https://twitter.com/kanekotic)) @[ClimatePartner](https://www.climatepartner.com).
</small>

---

{{% section %}}

# The monolith 🤒

<img src="/images/monolith.png" width="500"/>

{{% note %}}
- There was a time we all have to work on the same code base
- You release a big thing and pray it works 
- You go through big cycles of validating the entire thing to reduce Failure rate
- You need big teams only to validate, it makes the release cycle bigger
{{% /note %}}

---

# The microservice 🥳

<img src="/images/microservice.png" width="500"/>


{{% note %}}
- we love the concept because it means work in smaller things
- we can break less stuff so it gives us more confidences
- we depend on less people to achieve what we want
{{% /note %}}

{{% /section %}}

---


{{% section %}}

<img src="/images/bye.jpeg" width="700"/>

###### Awesome! questions?!

---

<img src="/images/waitasec.jpg" width="700"/>

###### or is it not finish...

{{% /section %}}

---

{{% section %}}

### Can there be problems with microservice?

---

# Did you had any of this cases?
- Before we release a new version we need to sync deploys with another team.
- Our application was down but is not our issue.
- Our service was working and scaling fine until the team X started using us.
- ...

---

### Dam You Microlith!

<img src="/images/microliths.jpg" width="700"/>

{{% note %}}
- when you have synchronous calls to other service you are not decoupled from them
- There is even cascading possible without your knowledge
- your boundaries are not defined
- slow services are forced to scale by faster services
- additional latency
{{% /note %}}

---

# effectively is a broken down monolith

{{% /section %}}

---

{{% section %}}

#### what got lost in translation?

<img src="/images/lostintranslation.jpg" width="400" />

---

# Domains != Resources

{{% note %}}
- You are thinking in Domains being resources, this comes from the CRUD mentality
- domain driven design is about thinking on a process as a bounded context
{{% /note %}}

---
 
# Independency Data != Only my data

{{% note %}}
- A single source of data means that whenever you need that data you have a direct dependency
{{% /note %}}

---
 
# synchronous != Faster

{{% note %}}
- A single source of data means that whenever you need that data you have a direct dependency
{{% /note %}}



{{% /section %}}

---

{{% section %}}

# We are doomed!!!

<img src="/images/timetopanic.jpg" width="700"/>

---

<img src="/images/outofhere.jpg" width="700"/>

###### questions???...

---


<img src="/images/notyet.gif" width="700"/>

###### ok!

{{% /section %}}

---

# So what do we do?!

---

{{% section %}}

# The Naive Solution
### circuit braked Microlith

<img src="/images/greenlantern.png" width="500"/>

---

<img src="/images/circuitbreakerdesignpattern.png" width="1000"/>

---

✔️ We don't fail continuously if some other service fails

❌ We silently don't finish the entire process requested

❌ We require all chain of dependencies to be called

❌ We force other services to scale to our needs

❌ Data is mutable so errors will be propagated and not solvable

{{% /section %}}

---

{{% section %}}

# A Better Solution
### The Outbox Pattern

<img src="/images/reactivehero.jpeg" width="700"/>

---

## Reactive Microlith

<img src="/images/reactivemicroliths.jpg" width="700"/>

##### wait still microlith?!

{{% note %}}
- Decouple using Pub/Sub (ex. kafka, kinesis)
- Consume the models from other services you need
- Broadcast your models to others
- Strong consistency on the outbox, eventual consistency in the service DB (if you have one) 
{{% /note %}}

---

✔️ We don't fail continuously if some other service fails

✔️ We always finish our process and promise the rest will be done 

✔️ We just need ourselves to do what we promise

✔️ Fast services will be fast, and slow services can go slow

❌ Data is mutable so errors will be propagated and not solvable

{{% /section %}}

---

{{% section %}}

# An Even Better Solution
### Event Sourcing Journal

<img src="/images/ironman.png" width="700"/>

---

## Microsystem (almost)

<img src="/images/microsystemsalmost.jpg" width="700"/>

##### wait almost?!

{{% note %}}
- based on event sourcing the true is the event and not the result
{{% /note %}}

---

## Microsystem

<img src="/images/microsystems.jpg" width="700"/>

{{% note %}}
{{% /note %}}

---

✔️ We don't fail continuously if some other service fails

✔️ We always finish our process and promise the rest will be done 

✔️ We just need ourselves to do what we promise

✔️ Fast services will be fast, and slow services can go slow

✔️ Data is immutable so a change in our code can solve historical errors

{{% /section %}}

---

{{% section %}}

<img src="/images/end1.png" />

---

<img src="/images/end2.jpg"/>

---

<img src="/images/end3.jpg" />

{{% /section %}}
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
- Our service was working and scaling fine until the team X started using us.
- ...

---

### Dam You Microliths!

<img src="/images/microliths.jpg" width="700"/>

{{% note %}}
- when you have syncronous calls to other service you are not decoupled from them
- There is even cascading possible without your knowledge
- your boundaries are not defined
- slow services are forced to scale by faster services
- aditional latency
{{% /note %}}

---

# efectively you have a monolith broken into pieces

{{% /section %}}

---

# We are doomed!!!

<img src="/images/timetopanic.jpg" width="700"/>

---


{{% section %}}

# Where are we failing?

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
 
# SYNC != Faster

{{% note %}}
- A single source of data means that whenever you need that data you have a direct dependency
{{% /note %}}



{{% /section %}}

---

# Any Alternative?!

---

{{% section %}}

# The Naive Solution
### circuit braked Microliths

<img src="/images/greenlantern.png" width="500"/>

---

<img src="/images/circuitbreakerdesignpattern.png" width="1000"/>

---

✔️ We dont fail continuesly if some other service fails

❌ We can lose data and dont finish the process requested

❌ We require all chain of dependencies that slows the service

❌ We force other services to scale to our users needs

❌ Data is mutable so errors will be propagated and not solvable

{{% /section %}}

---

{{% section %}}

# A Better Solution
### The Outbox Pattern

<img src="/images/reactivehero.jpeg" width="700"/>

---

## Reactive Microliths

<img src="/images/reactivemicroliths.jpg" width="700"/>

##### wait still microliths?!

{{% note %}}
- Decouple using Pub/Sub (ex. kafka, kinesis)
- Consume the models from other services you need
- Broadcast your models to others
- Strong consistency on the outbox, eventual consistency in the service DB (if you have one) 
{{% /note %}}

---

✔️ We dont fail continuesly if some other service fails

✔️ There is no data loss and the process will finish 

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

✔️ We dont fail continuesly if some other service fails

✔️ There is no data loss and the process will finish 

✔️ We just need ourselves to do what we promise

✔️ Fast services will be fast, and slow services can go slow

✔️ Data is inmutable so a change in our code can solve historical errors

{{% /section %}}

---

# Questions?

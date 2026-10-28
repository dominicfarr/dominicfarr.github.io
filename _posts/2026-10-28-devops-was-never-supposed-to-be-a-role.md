---
layout: post
title: "DevOps was never supposed to be a role"
date: 2026-10-28
tags: [devops, culture, careers]
---

Not long ago I worked with a startup where one of the developers had the title DevOps. Most of their day went on operations and the Terraform-based deployment pipelines, and they were often asked to do late-stage testing. Any ideas they had for the front end or the back end were blocked by the people who owned those parts of the system. Their overriding mode came from the operations playbook: keep things stable and secure, and resist any change that might threaten either. There's nothing wrong with that in itself. But when so little of your work is development, it's fair to ask why Dev is in your title. From conversations with my wider network, this is more common than I thought.

DevOps was meant to tear down the wall between the people who build software and the people who run it. On that team the wall was back, and it had a job title.

It wasn't always like this. When the word was new, it described a way of working, and nobody had it on their contract.

## Before it had a name

When Policy Expert was founded in early 2010, the cloud was still young. We were the first financial company we knew of to build on it, using managed resources so we could deliver faster than we could by owning and hosting our own data centres. DevOpsDays had only just started, and Flickr had recently shown the world it could deploy more than ten times a day. *Continuous Delivery* by Jez Humble and David Farley was the source for continuous delivery, a progressive idea back then, and in 2011 Heroku co-founder Adam Wiggins gave us the [Twelve-Factor App](https://12factor.net/) methodology. We absorbed these sources and tried to follow what they prescribed.

We were small: just a few engineers and the CTO at first, with testers and business analysts a little later. We didn't care about titles. We just worked at delivering business impact, in a cross-functional way. Some of us were stronger at architecture and others at JavaScript or the back end, but all of us worked across data, web, deployment and operations. What you built, you owned: its monitoring and health in production, and the migrations, backups, patching and scaling that came with it. We had one rule we took seriously: if you do something more than three times, automate it. Capistrano scripts shipped our code.

We didn't call any of this DevOps. It was just the philosophy of how we worked.

## When it became someone's job

As we grew, deploying to AWS took more and more work. We built a CI pipeline with Jenkins and then TeamCity, and our own system, Nessie, handled provisioning, staging and deployment through its API. Before long, looking after Nessie became someone's full-time role. We called that role platform development, and we were careful about what it meant. The platform developers didn't take over operations. Developers still owned their services and kept watch over their health, and when something broke in production, developers and the platform team worked on it together. What the platform team did was make the Ops side easier and more secure. Nobody went into production to read logs; you talked to Nessie. If you needed a production-like environment to test a tagged build, you talked to Nessie and got back a URL. Adding a secret worked the same way. Today we'd call Nessie an internal developer platform.

I once casually called them the DevOps team, and the friendly push-back I got from the developers settled it for me: DevOps was something all of us still did, and it couldn't be handed to one team.

## How a way of working became a job title

Meanwhile, "DevOps" started appearing in job descriptions. My sense is that the recruitment business latched onto the word first. It was a handy way to filter CVs and to price a role. The label spread faster than the meaning, and over the years the meaning thinned.

Jez Humble saw it early. In 2012 he wrote [There's No Such Thing as a "Devops Team"](https://continuousdelivery.com/2012/10/theres-no-such-thing-as-a-devops-team/), arguing that creating one just adds a third silo between development and operations. His post put into words what that debate with our developers later settled for me.

## If DevOps is your title

There's nothing wrong with you or your work. The title is the problem, because it describes a philosophy instead of a job. Google's [comparison of platform engineering and DevOps](https://cloud.google.com/discover/platform-engineering-vs-devops) puts it well: DevOps is the cultural goal, and platform engineering is a discipline that serves it by building an internal developer platform, a set of self-service tools that takes difficult, repetitive work off development teams. Developer experience is what that platform is for: how easy it is for developers to get their own software into production and keep it running. If that's most of your work, platform engineer is a more honest title. If your work is keeping production reliable alongside the people who build it, [site reliability engineering](/glossary/sre/) is closer.

## Take an honest look at your week

Whatever your title, look at what you actually spent your time on. Do you develop and operate the same things, or mostly one or the other? If most of your development is building tools that make other developers' lives easier, that may really be platform engineering, and it deserves a name that says so. Then ask whether your title helps people talk to each other and deliver, or whether it's quietly building a silo. DevOps was meant to tear down a wall, so it's worth checking your title isn't holding one up.

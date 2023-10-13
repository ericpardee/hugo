---
title: Markdown Resume
authors: [{'name': 'Eric Pardee'}]
published: 2023-10-12
---

# Markdown Resume

Creating multiple versions of resumes for different roles you apply for in Microsoft Word or Google Docs, keeping track of the differences, syncing some differences, publishing to PDF, etc. It's a recipe for disaster.
WHen i found myself in this mess, I found a way out with Markdown, Pandoc, some CSS and git magic.

![Building Block Resume](/building-block-resume.png)
DALL·E 3: _"Graphic for a blog post representing a resume, where each section constructed from building blocks, like a modular resume"_

## The Problem

I was applying to different jobs but the role of each job can vary greatly.

I clumsily would open a copy of my resume (which should I use, the one on Dropbox, OneDrive, my local computer...), make some modifications, personalizations, 'print to pdf', then ship off the PDF.

However, after a while, the drift in that/those Word Doc(s) was bad... Like really bad. Somehow there were typos. I'd forget if this version had the latest changes, etc.

I noticed that I recently shipped some resumes with typos, formatting messes, etc. and it was embarrassing.

## There Must Be a Better Way

Like any normal person in 2023, I did the sane thing and asked ChatGPT what to do.

I started with:
> Is there building block resume creation software?
>
> For example, I want to cater my resume to the role but keep certain parts (blocks) the same

After a few back and forths, I liked the idea of using Markdown... Hell, this here very blog is written in markdown. With Markdown, I can keep things clean, I can make the resume modular. For example, each section:

- Heading
- Experience
- Skills
- Certifications
- Education

Each section can be their own little Markdown file and then I can use pandoc to combine them.

I can also do things like add dynamic content. For example, I like to use different emails depending on who I am sharing my resume with. With a little `Makefile` and some `envsubst`, voila.

Of course someone else had already thought of this and I respectfully stole a lot of my work from Mr. Vid Luther: <https://luther.io/markdown-resume/>. I essentially cloned his GitHub repo, divided up his `resume.md` into markdown sections, and added a Makefile to compose the final PDF.

## The Final Result

I love it.

I can have resumes for all the potential roles I'd entertain at some point:

- Director of SRE / DevOps
- SRE / DevOps Manager
- Senior Director, IT
- Principal Platform Architect
- Solutions Engineer
- Head of Security Architecture, Engineering, and Delivery
- CTO
- Lead IT Architect
- Lead Solution Architect
- Tech Lead, DevOps Infra
- AI Solutions Engineer

But now I can keep these organized, easily updated and no longer worry about MS Word issues or having Word installed. I could even add GitHub actions to do the rendering outside my box if the need arises.

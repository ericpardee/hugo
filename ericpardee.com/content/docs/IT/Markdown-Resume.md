---
title: Markdown Resume
authors: [{'name': 'Eric Pardee'}]
published: 2023-10-12
---

# Crafting the Perfect Resume with Markdown

Navigating the complexities of tailoring resumes for distinct roles using tools like Microsoft Word or Google Docs can be a treacherous journey. Juggling multiple versions, ensuring consistent updates, and the final step of exporting to PDF can lead to inadvertent errors and inconsistencies. It was during one such chaotic episode that I stumbled upon the magic of Markdown, combined with Pandoc, CSS, and a sprinkle of git.

![Modular Resume Concept](/building-block-resume.png)
DALL·E 3: _"Graphic for a blog post representing a resume, where each section constructed from building blocks, like a modular resume."_

## The Dilemma

In my exploration of potential new professional horizons, I was often required to modify my resume to cater to the specific nuances of each role. This led me to a labyrinth of resume versions—stored on Dropbox, OneDrive, and my local computer. The challenge was not just in choosing the right version but also in maintaining a consistent and error-free document.

To my dismay, I realized that I had sent out resumes riddled with typos and formatting inconsistencies. The embarrassment was palpable.

## The Epiphany

In true 2023 fashion, I turned to my trusted friend, ChatGPT, for guidance.\
I prompted:

> "Is there a software that allows for modular resume creation?"
>
> "I aim to tailor my resume for specific roles while retaining certain consistent sections or blocks."

The conversation that ensued introduced me to the idea of using Markdown, CSS, wkhtmltopdf and Pandoc. Interestingly, the very blog you're reading is penned in Markdown. This simple markup language allowed me to deconstruct my resume into distinct sections:

- Heading
- Experience
- Skills
- Certifications
- Education

Each of these segments became individual Markdown files. Using Pandoc, I could seamlessly merge them. Moreover, I could introduce dynamic content, such as customizing my email based on the recipient. A judicious use of `Makefile` and `envsubst` made this a breeze.

While the idea was innovative, I wasn't the pioneer. I drew inspiration from Mr. Vid Luther's approach, as seen here: <https://luther.io/markdown-resume/>. I adapted his GitHub repository, segmenting his `resume.md` into distinct markdown sections, and incorporated a Makefile to craft the ultimate PDF resume. By leveraging git, I can create a branch for each role and a tag for every job application.

## The Revelation

The transformation has been remarkable.

Now, I have the ability to tailor resumes for an array of roles I'm passionate about:

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

These are not just organized and up-to-date, but they're also free from the earlier hassles of software compatibility, installation or licensing woes. The possibility of integrating GitHub actions for external rendering is an exciting avenue I might explore soon.

In a world where first impressions matter, having a polished and tailored resume can make all the difference. And with Markdown, I've found my perfect tool.

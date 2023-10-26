---
title: Ask Your Data Naturally
authors: [{'name': 'Eric Pardee'}]
---

# Simplifying Security Questionnaires with Natural Language: LlamaIndex & LLM

Healthcare security questionnaires can be a daunting task, especially when you're inundated with them in various formats. However, imagine a solution where you could use natural language queries your security policies to get responses effortlessly. In this post, I'll share how I harnessed the power of OpenAI's Models and the Retrieval Augmented Generation (RAG) paradigm to turn this dream into reality.

![Simplifying Security Questionnaires with Natural Language: LlamaIndex & LLM](/llama-rag-security-questionnaire.png)

## The Challenge

In my prior role as Senior DevOps & Infrastructure Engineer, I was suddenly thrust into an unexpected whirlwind at the start of 2023. Our Director of Security and Compliance and the IT Analyst, significant pieces to our operation, left the company in December 2022. The situation further escalated when the Head of Engineering, who had pledged to share the increased workload, exited in early January 2023. The aftermath? Exhausting 12-15 hour workdays, weekends dedicated to untangling messes, and the daunting task of addressing healthcare security questionnaires, each laden with 200+ questions, from potential partners.

Each questionnaire had its unique format or website, making standardization impossible. While we had tools like [Tugboat Logic / OneTrust](https://chrome.google.com/webstore/detail/tugboat-logic-extension/icnjdbfcgobdmmkpaabkeoflmfbdipad) at our disposal, they weren't the magic bullet solution I was hoping for.

## The Thought

Having experimented with OpenAI's ChatGPT since November 2022, an idea began to germinate. Could I feed our security and compliance policies into this AI and then easily retrieve the answers for these questionnaires? My interest piqued further when a mentor introduced me to [Lenny Newsletter's chatbot guide](https://www.lennysnewsletter.com/p/i-built-a-lenny-chatbot-using-gpt) and [LlamaIndex](https://docs.llamaindex.ai/en/stable/).

Though aware of the privacy concerns related to sending data to OpenAI, I was comfortable with the generic nature of our Security Policies and I took measures to obfuscate company-specific details.

## What is RAG

Retrieval Augmented Generation (RAG) offers a unique approach to augment LLM with custom data. The two primary stages in a RAG system are Indexing and Querying.

![RAG System](/rag-system.png)

## Taking the Leap

I extracted our policies from Google Drive and sanitized the data for safety.

Using the [Lenny Chatbot Colab Notebook](https://colab.research.google.com/drive/1p2AablavDkSXly6H-XNLoSylMtoz7NDG?usp=sharing), I managed to index the data, making it query-ready. However, the limitation of Google Colab Notebook led me to consider builiding a simple web application. Drawing inspiration from Lenny's example and pseudocode, and with a dash of help from ChatGPT, I crafted a tool that could:

- Index the policies and save a vector index as a JSON file.
- Offer a user-friendly web interface for queries.
- Utilize ChatGPT to generate answers based on the indexed data.

## The Outcome

By April, I had a prototype operational on Google Colab:

{{< rawhtml >}}

<video width=100% controls>
    <source src="/2023-04-12_colab.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>

{{< /rawhtml >}}

Soon after, a polished version was ready, enabling my colleagues to harness its power:

{{< rawhtml >}}

<video width=100% controls>
    <source src="/2023-04-16-ui.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>

{{< /rawhtml >}}

![First Reveal of bot](/first-reveal-of-bot.png)

I affectionately named it "Quinne Bot", a nod to our former Director of Security and Compliance whose expertise was unparalleled.

## Evolution of the Idea

Fast forward 6 months, and creating such a bot has become considerably simpler. Streamlit's [guide on building a chatbot with LlamaIndex](https://blog.streamlit.io/build-a-chatbot-with-custom-data-sources-powered-by-llamaindex/) was a testament to this. With the foundational knowledge from this guide, I enhanced the bot by integrating features like:

- File uploads via:
  
  `.zip` archive
  ![zip archive](/zip-archive.png)
  [S3 bucket](https://aws.amazon.com/s3/)
  ![s3 bucket](/s3-bucket.png)
  SFTP Server
  ![sftp server](/sftp-server.png)
  Git repository
  ![git repo](/git-repo.png)

- Advanced configuration settings for personalized user experience:
![Advanced Configuration Settings](/adv-conf-settings.png)

For those interested, the code is available [here](https://github.com/ericpardee/llamaindex-chat-on-streamlit). To experience it firsthand, feel free to drop me an email (those OpenAI credits aren't free ;).

## Onward and Upward

While some might consider RAG a hack, it can still be better than finetuning. LlamaIndex is rapidly evolving too; from a tree-index builder to a fairly comprehensive framework able to leverage data in LLM applications. The potential of LlamaIndex combined with LLMs is exciting and I am eager to delve deeper.

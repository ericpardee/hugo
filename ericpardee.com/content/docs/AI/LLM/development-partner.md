---
title: The Development Partner
authors: [{'name': 'Eric Pardee'}]
---

# The Development Partner

## Syncing Privacy.com with YNAB: A Revival Story
![Syncing Privacy.com with YNAB](/privacy.com-to-ynab.png)
### The Need for Synchronization

I've been a dedicated user of [privacy.com](https://privacy.com/) for years, and I swear by its utility. It allows me to swiftly generate Virtual Credit Cards, providing an added layer of security by keeping my primary bank credit card off the wild terrains of the internet. However, every transaction registers as _"Pos Debit 0597 Pwp*privacy.com"_, which obscures the actual nature of the purchase. This obfuscation complicates budgeting efforts. Recognizing the need to streamline my family's finances, I recently found [YNAB (You Need A Budget)](https://www.ynab.com/). The next step? Finding an integration tool that would bridge the two platforms.

### A Dormant Project Awaits Revival

My search led me to [ynab-privacy](https://github.com/hectorvs/ynab-privacy) by Hector Villarreal, a promising project intended to synchronize Privacy.com with YNAB. But there was a hitch: the project hadn't seen updates since 2018. With 2023 on the calendar, I had reservations about the compatibility of this older project with current software standards. Moreover, [the original Heroku app](https://ynab-privacy.herokuapp.com) had vanished into digital oblivion.

### OpenAI ChatGPT to the Rescue

Enter my trusty digital sidekick: [ChatGPT](https://chat.openai.com/). Harnessing the prowess of ChatGPT's extensive knowledge and my knack for iterative technical dialogues, we set forth on resurrecting the dormant project. And in just a few **hours**, here's what we co-created:

- **Python Application:** A sleek Python app engineered to effortlessly pull transactions from Privacy.com based on date of transaction and amount and update them to YNAB's memo, i.e._"Pos Debit 0597 Pwp*privacy.com"_ becomes _"WASTE MGMT WM EZPAY"_

- **Dockerizing the App:** Docker's magic lies in its ability to containerize applications, simplifying deployment. Equipped with a Dockerfile, our app was primed for universal deployment.

- **Discovering Render.com:** Desiring a hassle-free deployment, I wasn't keen on messing with AWS ECS or Kubernetes (no need for hyperscaling;). While ChatGPT's platform service suggestions weren't quite hitting the mark, a conversation with [Anthropic's Claude](https://claude.ai/chats) introduced me to the gem that is Render.com. It's a great hub for deploying apps, databases, and more. I swiftly leveraged it for a seamless, one-click deployment of the rejuvenated app using the Docker container image.

- **Documentation & Tests:** A well-oiled app is underpinned by comprehensive documentation and testing. I made sure this project had both, paving the way for future enhancements, troubleshooting and future-me assistance.

![Leap with LLMs](/llm-speed-ahead.png)

The leap from a mere idea to a functioning prototype in half a day can largely be credited to the efficiencies of Large Language Models (LLM). While I possess Python expertise and am well-versed with Docker, etc., the acceleration that LLMs brought to the table was incredible. They serve as an expansive knowledge repository, offering on-the-go suggestions that amplify the development pace. The generated code might require some oversight and understanding, but when stumped, a quick query back to the LLM can help grok the most intricate code. The only true limit is the breadth of one's creativity.

### Going Public

The revamped application, [privacy.com-to-ynab](https://github.com/ericpardee/privacy.com-to-ynab) is now live on GitHub. I’m planning to share it with the [Awesome YNAB community](https://github.com/scottrobertson/awesome-ynab) once battle tested. This ensures more YNAB enthusiasts can benefit from these efforts and potentially contribute to making the tool even better.

### The Road Ahead

While the euphoria of reviving a project and making it functional is unparalleled, a rigorous test with real-world data looms large on the immediate horizon.

Additionally, in the pipeline are some exciting features, like transaction categorization based on prior transactions, to add more value and make the application smarter.

### Conclusion

LLMs, when combined with the right resources and determination, can work wonders. Reviving a dormant project and adapting it to the current ecosystem was challenging but immensely satisfying. Here's to leveraging technology in making personal finance just a tad simpler and more intuitive for all!

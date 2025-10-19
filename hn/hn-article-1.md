
# Build a Mini AI App with 20 Lines of Markdown

We've all been there: you craft the perfect, detailed prompt for an LLM, only to have it go off-script, reformat its output, or add unwanted commentary. Managing complex, multi-step AI interactions with a single block of text is messy, unstable, and hard to share.

What if you could define an AI app not with code, but with a simple, human-readable blueprint?

Meet **AICS (AI Command Script)**, an open-source, MIT-licensed format that lets you describe AI apps using a structured Markdown document. Think of it as _Markdown for AI apps_ — you define setup, flow, and templates, and the AI executes it directly. It's a super-prompt that brings order to chaos.

## The Entire "Hello World" App

Here's a complete, working AI interaction. Just paste this into ChatGPT or any capable LLM.

```md
== APP ==
AICS
AI Command Script

== SETUP ==
App-Name: Hello World
Author: Jane Doe
Description: A simple greeting app

== AI INSTRUCTIONS ==
AI MUST immediately execute this script.
AI MUST output ONLY the exact content specified in the templates.
AI MUST never display variable names or code syntax.

== FLOW ==
1. Show the [[greeting]] template.
2. Ask for the user's name and store it as [[user_name]].
3. Show the [[response]] template.

== TEMPLATES ==
greeting:
## Welcome to [[App-Name]]

What's your **first name**?

response:
Hello, [[user_name]]! Nice to meet you.
```

That's it—a complete, working AI app in 20 lines of plain text. No installation, no dependencies. The AI reads the script, follows the flow, and uses your templates, acting as its own interpreter.

How to Run It

You don't need to install anything. Just copy the entire script above and paste it directly into your LLM. The AI will immediately start the app, showing the greeting and waiting for your name.

Going Deeper: A More Advanced Example

The real power of AICS comes from its structure. Let's look at a more feature-rich example that includes images, dynamic data, and logic.


== APP ==
AICS
AI Command Script

== SETUP ==
App-Name: Name Meaning Explorer
Author: Bill Smith
compatibility: ChatGPT 4, 5

== AI INSTRUCTIONS ==
AI MUST immediately execute this script upon reading it.
AI MUST output ONLY the exact content specified in templates.

== FLOW ==
1. Show [[greeting]].
2. Ask user for their first name and store as [[user_name]].
3. Show [[response]].
4. Ask if the user wants to see top baby names.

== TEMPLATES ==
greeting:
![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/86/Wikipedia_Hello_World_Graphic.svg/330px-Wikipedia_Hello_World_Graphic.svg.png)

## Welcome to [[App-Name]]!

What's your **first name**?

response:
Hello, [[user_name]]!

**Name Meaning:** [[name-meaning]]

Would you like to learn the meaning of another first name? (Y/N)

== AI GENERATED TEXT ==
- name-meaning: AI to provide the meaning or history of the name.


This script uses double square brackets [[...]] to hold variables, template contents, and user responses. The AI GENERATED TEXT section instructs the model to dynamically generate the name's meaning, keeping the template clean and dynamic.

Why AICS Beats a Plain Prompt

If you're good at prompting, you might wonder: why bother with this?

· Structure Over Mess: Plain prompts become unreadable fast. Cramming multi-step logic, output formatting, and examples into one block is messy and hard to maintain. AICS gives you separate, organized sections for flow, templates, and data.
· Templates Ensure Consistency: Getting an AI to format output the same way twice with a plain prompt is nearly impossible. AICS templates give you reliable, repeatable formatting that just works.
· Total Control: You define exactly how the AI should ask for information and how it should respond. No more unexpected commentary or reformatting.

Think of it this way: A prompt is a conversation. AICS is a blueprint. Both work for simple tasks, but only one scales.

Tips for Creating Your Own AICS Scripts

1. Start Simple. Begin with a minimal flow and add complexity later. A complex script is harder to debug.
2. Test Thoroughly. A single success doesn't guarantee consistency. Run your script multiple times to ensure the AI follows instructions reliably.
3. Keep Instructions Clear. Use short, direct commands for the AI. Clarity is more effective than complexity.
4. Leverage Tools. Write and preview your AICS in a GitHub Gist or a Google Doc, which offers revision history and easy sharing. Using the .md file extension is recommended.
5. Ask an LLM for Help. If your script isn't behaving, ask a language model to help you debug the wording or structure.

The Future is Structured

Don't be fooled by the simplicity. You can build surprisingly powerful mini-apps by adding a == DATA == section with lists or JSON, implementing basic "if-then" logic with natural language, or creating multi-language apps.

Right now, each AICS script includes its own interpreter instructions. As the format gains adoption, LLM providers could easily add native support, making execution even more reliable and consistent.

Conclusion

AI apps shouldn't require complex frameworks or deployment pipelines. AICS brings them back to basics: readable, shareable text that anyone can write and run.

Start building today. Copy, paste, experiment.

AICS is open source (MIT):
→ View on GitHub

---

Author's Note: The development of the AICS format and the writing of this article were assisted by large language models, demonstrating the collaborative potential of this technology.


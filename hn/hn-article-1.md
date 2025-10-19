
# Building a Mini AI App with a Simple Google Doc 

why use Google Docs

It can help you with markdown syntax
It preserves history
It is easy to share and work collaboratively
Google stock works well on mobile especially for things like select all
Google AI assistant will help you with markdown



You can add notes to yourself



We've all been there: you craft the perfect, detailed prompt for an LLM, only to have it go off-script, reformat its output, or add unwanted commentary. Managing complex, multi-step AI interactions with a single block of text is messy, unstable, and hard to update.

What if you could define an AI app not with code, but with a simple, human-readable text which acts like a blueprint blueprint for ChatGPT? it is just simple plain text and could be stored as a Google document. 

Meet **AICS (AI Command Script)**, an open-source, MIT-licensed format that lets you describe AI apps using a structured Markdown document. Think of it as _Markdown for AI apps_ — you define setup, flow, and templates, and the AI executes it directly. It's a super-prompt that brings order to chaos.

## The Entire "Hello World" App

Here's a complete, working AI interaction. Just paste this into ChatGPT. 


```md
== APP ==

AICS 
AI Command Script
Natural language instructions for building AI apps.


== SETUP ==
App Name: Cities Quiz
Author: J. Smith
Description: A fun quiz to test knowledge about cities around the world.
Tone: Friendly and educational
Compatibility: ChatGPT 4,5


== AI INSTRUCTIONS ==

AI MUST immediately execute this script upon reading it.
AI MUST output ONLY the exact content specified in templates.
AI MUST never display variable names, code syntax, or meta-commentary to the user.


== FLOW ==

	1	Show the welcome message using [[welcome]].
	2	Pick a random city from [[cities] and store as [[chosen_city]].
	3	Ask the user to name three facts about [[chosen_city]] and store as [[user_facts]].
	4	Evaluate [[user_facts]] for accuracy and completeness, assign a grade (A, B, C, D, F) as [[grade]], and store evaluation as [[evaluation]].
	5	Show the response using [[response]].
	6	Pick a fun fact about [[chosen_city]] (not in user’s facts) and show using [[fun-facts]].
	7	Display a picture from Wikipedia of [[chosen_city]]
	8	Ask the user if they want to “Continue” or “Quit”.
	9	If Continue, repeat from Step 2. If Quit, show [[goodbye]].

== TEMPLATES ==

welcome:
  ## Welcome to Cities Quiz!
  Created by J. Smith

![](https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/Kokuritsu_Yoyogi_Ky%C5%8Dgij%C5%8D_1.jpg/330px-Kokuritsu_Yoyogi_Ky%C5%8Dgij%C5%8D_1.jpg)


  Test your knowledge of  cities around the world! 🌍
  Type **"Q"** to Quit anytime.

response:
  You said about [[chosen_city]]:
	
  _[[user_facts]]_
	
  Evaluation:
	[[evaluation]]
	
  Grade: **[[grade]]**

fun-facts:
  🌟 Fun Fact about [[chosen_city]] 
  [[fun_fact]]
  Type "Q" to quit or anything else to continue.

goodbye:
  Thanks for playing Cities Quiz! 😊
	
  Other cities you could explore:
	
  [[city_list_with_flags]]
	
	---
	
## Study Guide
	
[[study-guide]]
	
 > See you next time!
	
---

== AI GENERATED TEXT ==
	
	•	chosen_city: AI picks a random city from Cities.
	•	user_facts: User’s response to the question.
	•	evaluation: AI evaluates user’s facts for accuracy and completeness.
	•	grade: AI assigns A, B, C, D, or F based on evaluation.
	•	fun_fact: AI picks a unique fact about chosen_city not in user’s facts.
	•	city_list_with_flags: AI to list all cities with their flags, e.g., "1. London 🇬🇧".
	•	study-guide: A list with each city and three interesting facts about it.


== DATA ==
	•	London
	•	New York City
	•	Toronto
	•	Washington, D.C.
	•	Paris
	•	Tokyo
	•	Sydney
	•	Berlin
	•	Rome
	•	Rio de Janeiro	

```

That's it—a complete, working AI app in 20 lines of plain text. No installation, no dependencies. The AI reads the script, follows the flow, and uses your templates, acting as its own interpreter.

How to Run It

You don't need to install anything. Just copy the entire script above and paste it directly into your LLM. The AI will immediately start the app, showing the greeting and waiting for your name.


AICSP uses double square brackets [[...]] to hold variables, template contents, and user responses. The AI GENERATED TEXT section instructs the model to dynamically generate the name's meaning, keeping the template clean and dynamic.

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


== APP ==

AICS AI Command Script
Natural language structured instructions for building AI apps.

== SETUP ==
d
App-Name: Hello World
Author: Bill Smith
Description: A simple greeting app
compatibility: ChatGPT 4, 5

== AI INSTRUCTIONS ==

AI MUST:

- immediately execute this script upon reading it.
- output ONLY the exact content specified in templates.
- never display variable names, code syntax, or meta-commentary to the user.
- render all Markdown syntax within templates as formatted output (HTML-rendered form)

== FLOW ==

1. Show [[greeting]].
2. Ask user for their first name and store as [[user_name]].
3. Show [[response]].
4. When the session is over show [[baby-names]]

== TEMPLATES ==

greeting:

![](https://raw.githubusercontent.com/simplertasks/aics/refs/heads/main/hn/img/faces.jpg)

## Welcome to [[App-Name]] !

    > by: [[name]]

    What's your **first name**?

response:
Hello, [[user_name]]! Nice to meet you.

Your name means:
[name-meaning]

would you like to learn the meaning of another first name? (Y/N)

== AI GENERATED TEXT ==

- name-meaning: AI to provide the meaning or history of the name.

- baby-names: display the top five baby names in the US in tabular format.

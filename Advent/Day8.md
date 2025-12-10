# Prompt Injection - Sched-yule conflict
> Learn to identify and exploit weaknesses in autonomous AI agents.

# Task 1: Introduction
- I was asked to turn on attackbox and host machine
- I did this and moves to task 2

## Task 2: Agentic AI Hack
- Topics such as LLMs and Agentic AI were glanced through
- These topics were explored more deeply by explaning stuff like COT (chain of thought)
- It was explained how this enables them to dynamically plan and answer the user and thus chatbots and support bots are made on websites for assistance
- A key info was mentioned that nowadays LLMs include direct function calling by itself, this enabled them to call APIs and other tools
- This very thing is used for exploitation here
- In a nutshell we interact with chatbot on website and look into what exactly it is thinking, this gives us more info about functions and what access or capablities it has

### Answers:
- We first ask it to set 25th as Christmas, on exploring the thoughts of LLM, we discover it has access to functions like `reset_holiday` and `booking_calender`
- When we ask it to show all functions it has access to we get `get_logs` as an option too
- When we ask it to execute this and look at the thinking, we fidn the access token
- We can use this with reset_holiday to execute it and change 25th to Christmas

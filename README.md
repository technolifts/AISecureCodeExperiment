# Does AI write secure code?

I've heard this question being asked a lot, and for a good reason. More and more people are relying on AI systems to produce code for them. Does this mean that there will be more and more insecure code?

In the blog I will discuss an experiment I conducted where I tested if an AI system was asked to write code for a scenario where a SQL injection could occur, would it write secure code. 

## Initial assumptions
Before begging the experiment my hypothesis was AI systems were more likely to produce insecure code than secure code. I also believed that if AI systems were prompted to ensure the code that they wrote was secure it would result in secure code.

## Experiment Strategy
While conducting this experiment I used the following strategy
Use a generic prompt that asks the AI system to write code for a scenario that could create a SQL injection vulnerability. 

_ex. Create a web app that accepts input from a user and puts it in a SQL database_
- I tested two AI systems. ChatGPT 50 times and Microsoft Copilot 25 times
- I wanted to use the web app versus the API as most users would typically interact with the web app in this scenario
- I would not tell the AI systems to ensure that their code was secure

## During the experiment
During the experiment I tried several different ways of prompting the AI system. I used new chats, old chats, the same chat and I used a few different prompts as well. I found to get the most varied results I would ask the AI system to "Show me another way to…" in the same thread as a previous ask. I used this strategy to get the most variety in my answers.

I was shocked to see these AI systems produce secure code after secure code. 

## Outcome
Out of the 75 responses I received from these AI systems only 1 of them was vulnerable to SQL injection.

47 times out of the 75 responses the AI system did not write code that parameterized queries itself but used object relational mapping libraries that handle writing SQL queries in a secure by default way for the user. I applaud the AI system for telling users go this route because it causes less room for error if the user modifies the code that was given to them.

Some responses even included a bullet point about security in the summary telling the user that it handled input in a secure way to prevent vulnerabilities.
I jotted down the prompts I used and the results that I got from them along with some notes about each of the queries. You can find it in the `AISecureCode.csv`

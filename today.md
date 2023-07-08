```js
graph TD;
Start --> A
A(User) -->|what is the date today?| B(Agent);
B(Agent) -->|"`Thought: I can use the 
date_tool to get today's date.`"| C(Agent);
C(Agent) -->|"`Action 
'action': 'date_tool', 
'action_input: ''`"| D(Tool);
D(Tool) -->|Fri Jul 07 2023| C(Agent);
C(Agent) -->|Final Answer: Fri Jul 07 2023| B(Agent);
B(Agent) -->|The date today is Fri Jul 07 2023.| A(User);
A --> End
```
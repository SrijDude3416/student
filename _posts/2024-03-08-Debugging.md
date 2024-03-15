---
toc: True
comments: True
layout: default
title: Debugging
description: Going through debugging
type: tangibles
courses: {'compsci': {'week': 12}}
---

1. Start backend using Debugging
![](../../../images/debugging/Screenshot 2024-03-07 134058.png)
2. Set break point at the beginning of endpoint code
![](../../../images/debugging/Screenshot 2024-03-07 134201.png)
3+4. Start in frontend with split screen loading source for an API fetch using GET and Set break point on fetch, inside .then, inside .fetch
![](../../../images/debugging/Screenshot 2024-03-07 135126.png)
![](../../../images/debugging/Screenshot 2024-03-07 134708.png)
5 + 6. Run frontend, screen capture break at fetch while examining Body + press play on frontend, observe stop inside of backend
![](../../../images/debugging/Screenshot 2024-03-07 135423.png)
7: Press step over on backend until you have obtained data from database, screen capture Python Object
![](../../../images/debugging/Screenshot 2024-03-08 133924.png)
8: Press play button to end backend debugging session.

9: Return to frontend debug session

10: Step in until you see data, screen capture capturing break point and Data.
![](../../../images/debugging/Screenshot 2024-03-08 134632.png)


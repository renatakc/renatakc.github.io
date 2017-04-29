---
layout: post
title:  "I'll get there"
date:   2016-03-21 19:32:39
categories: 
---

It was one more SQL day, loads of exercises been punching my face. Yes, I am talking about that great Russian website, because they've just created several good exercises (Yes, I've being polite!). They're tough, but it is useful for my learning, so... let's keep doing them!

What did I learn today?

How to do subqueries in SQL, like this one:

```sql
SELECT PO.maker, PR.price
FROM Printer PR
INNER JOIN Product PO
ON PR.model = PO.model
WHERE PR.color = 'y' AND PR.price IN
(SELECT MIN(P.price) FROM Printer P WHERE P.color = 'y')
```

There's one particular test which I couldn't do. It is almost impossible. I asked for help for two software developers and, like me, they couldn't do this.

I won't post the exercise here because according to this website, it is against the rules and I can be kicked out.

That's it for today.
Thanks, bye!
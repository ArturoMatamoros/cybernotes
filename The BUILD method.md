## Your Complete Personal Study Method

I'm building this specifically around you: low focus, fragmented knowledge, needs to cover programming AND tools like Wireshark, has limited time, needs visible progress.

I'm calling it the **BUILD loop** so you have one word to remember when you sit down.

---

### The BUILD Loop

```
B — Break it down
U — Understand one piece
I  — Implement immediately
L  — Log what happened
D — Do it differently
```

Every single study session follows this loop. Every topic. Python, Wireshark, Linux, containers, everything.

Let me explain each step precisely.

---

### B — Break It Down

Before you open any book or tool, you spend **five minutes maximum** answering this question in writing:

_"What is the one specific thing I want to be able to DO at the end of this session?"_

Not understand. Not learn about. **Do.**

Bad examples:

- "Learn Python file handling" — too vague
- "Study Wireshark" — completely useless as a goal
- "Review networking" — not actionable

Good examples:

- "Write a Python script that opens a file and prints lines containing a keyword"
- "Capture live traffic in Wireshark and identify one DNS query manually"
- "Run a Docker container and access its shell"
- "Write a Bash script that checks if a service is running"

One sentence. One deliverable. Specific enough that at the end of the session you can answer yes or no: did I do this thing?

Write it at the top of your Obsidian lab note before you do anything else.

This step fixes the focus problem. Your brain needs a target. Without a target, 20 minutes disappear because you're vaguely consuming without direction.

---

### U — Understand One Piece

Now and only now you open the resource — book, documentation, video, whatever. But you read or watch with **one specific purpose**: find the minimum information needed to attempt your goal.

You are not reading the chapter. You are **hunting for one thing.**

Set a timer for **20 minutes**. That's your reading budget. When the timer ends, you stop reading regardless of where you are.

During those 20 minutes, when you find something directly relevant to your goal, you write it in your own words in the Obsidian note. Not copied. Rewritten.

If after 20 minutes you don't have enough to attempt something, that means your goal was too big. Break it down further.

**For low focus specifically:** 20 minutes is your maximum continuous reading block. After 20 minutes you must switch to doing something active. Reading for longer than this without producing output is where your focus collapses and you start re-reading the same paragraph.

---

### I — Implement Immediately

Close the book. Close or minimize every reference. Open your terminal, editor, or tool.

Now attempt the thing.

Here is the exact rule for when you get stuck:

**Stuck for less than 5 minutes** → keep trying, you're close

**Stuck for 5–10 minutes** → write in a comment exactly what you're trying to do and what's missing, then look up only that specific thing

**Stuck for more than 10 minutes with no progress** → your goal was too big, split it in half and do the smaller half first

That's it. That's the entire "getting stuck" protocol. It removes the anxiety because now being stuck has a procedure instead of being an open-ended panic.

**For Wireshark and tools specifically**, implement means:

- Open the tool
- Try to do the specific thing you read about
- If you can't find a button or option, look it up surgically
- Produce one screenshot or one output that proves you did the thing

You don't need to write code to implement. Implementation means producing evidence that you can do the thing.

---

### L — Log What Happened

After you finish implementing — whether it worked perfectly, partially, or completely broke — you spend **10 minutes writing the lab note.**

This is not optional and it is not extra work. It is part of the learning. Writing what happened forces your brain to consolidate what it just experienced.

Your log entry has exactly these five sections, and each one should be short:

```
GOAL: What I was trying to do

ATTEMPT: What I actually did (steps taken)

BROKE: What didn't work and what error or problem appeared

FIXED: What I looked up and what solved it

LEARNED: One sentence — what I now know that I didn't before
```

That's the whole note. It should take 10 minutes. If it takes longer you're overthinking it.

Over time these log entries become your most valuable resource. When you hit the same problem six months later you search your vault and find your own solution. When an interviewer asks "tell me about a time you debugged something" you have dozens of real examples.

---

### D — Do It Differently

This is the step most people skip and it's the one that separates people who remember things from people who forget them within a week.

After your implementation works, you spend **10–15 minutes deliberately modifying it.**

You change one variable. You break one assumption. You add one small feature. You apply it to a different input.

**For Python:**

- Change the input file to one that doesn't exist — what happens?
- Add a counter that tracks how many lines matched
- Make the keyword come from user input instead of being hardcoded

**For Wireshark:**

- You identified a DNS query — now find the response packet
- Apply a display filter to show only that one conversation
- Export the packet as a file

**For Linux commands:**

- Run the command with a different flag
- Try to break it with unexpected input
- Combine it with another command using a pipe

This step builds the "smanettone" behavior directly. You are practicing the habit of asking _"what else can this do? what happens if I change this?"_ That curiosity on demand — that is what the smanettone mindset actually is. It's not magic. It's a habit of deliberate variation.

---

## The Complete Session Structure

Here is your session laid out in time blocks. Total time: **60 to 90 minutes.**

```
[0:00 – 0:05]   B — Write your specific goal for this session
[0:05 – 0:25]   U — Read or watch with a timer, hunt for what you need
[0:25 – 0:55]   I — Implement. Attempt, get stuck, look up surgically, fix
[0:55 – 1:05]   L — Write your lab log in Obsidian
[1:05 – 1:20]   D — Modify, break, extend what you built
```

If your focus collapses during the Implement phase, use this rule: **5 minutes of attempt, 2 minutes of rest, repeat.** Short cycles. Don't try to force 30 minutes of continuous concentration if your brain doesn't work that way. Work with it, not against it.
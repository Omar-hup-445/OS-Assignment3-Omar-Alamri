# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Omar Alamri |
| **Student ID** | 445350256 |
| **University Email** | 445350256@std.psau.edu.sa |
| **GitHub Username** | Omar-hup-445 |
| **Repository Link** | https://github.com/Omar-hup-445/OS-Assignment3-Omar-Alamri |
---

## 🎥 Video Link

**Video Link**: https://drive.google.com/file/d/1jSSdCb_kF3AEi1RXzVzFwW0R_qegz5IG/view?usp=sharing

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`
**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---



## Your Development Log

### Entry 1 - November 11, 2026, 2:00 PM
**What I did**: Set up my repository, ran the starter, and implemented Feature 1.

**Details**:
- Forked the starter repository and named it OS-Assignment3-Omar-Alamri.
- Set my student ID to 445350256, then committed and pushed the change.
- Ran the original starter and saved its output. Multiple CPUs selected P1, causing IllegalThreadStateException.
- Added queueLock to ReadyQueue and protected add(), poll(), processOf(), and snapshot() using try/finally.
- Tested Feature 1 five times. All 15 processes completed in each run without exceptions or watchdog messages, but statistics errors and busy waiting remained.
- Committed and pushed Feature 1.

**Challenges**: After editing the code, I initially ran an old compiled version and saw the same queue errors.

**Solution**: Recompiled SchedulerSimulationSync.java with javac before running it again.

**Time spent**: Approximately 30 minutes of active work.

---

### Entry 2 - November 11, 2026, 4:30 PM

**What I did**: Implemented Feature 2 and fixed the race conditions in shared statistics.

**Details**:
- Added three separate ReentrantLocks to protect the shared counters.
- Used lock(), try/finally, and unlock() in the update methods and getters.
- The first test showed incorrect context switch and service time values.
- Recompiled the Java file and tested the updated code again.
- Ran five tests and checked the results of each run.
- All five tests showed 27 context switches, 15 completed processes, and 103012 ms total service time.
- Busy waiting remained and will be fixed in Feature 3.

**Challenges**: The first test showed incorrect statistics, and the terminal displayed strange characters.

**Solution**: Recompiled the updated Java file and adjusted the terminal settings so the numbers displayed correctly.

**Time Spent**: Approximately 25 minutes of active work.

---

### Entry 3 - November 11, 2026, 6:25PM

**What I did**:

Implemented Feature 3 by replacing busy waiting with a counting semaphore.

**Details**:

- Added a Semaphore to the ReadyQueue with 0 initial permits.
- Used release() when adding a process to the queue.
- Used acquire() to make CPUs wait for available processes.
- Added a method to wake waiting CPUs when all processes finish.
- Tested the program and verified all expected values.

**Challenges**:

The busy-waiting counter was still showing a value greater than 0 after updating the code.

**Solution**:

I compiled the updated code into a new build folder and ran it. All verification checks passed, and the busy-waiting counter became 0.

**Time spent**:Approximately 45 minutes of active work.


---

### Entry 4 - November 11, 2026, 9:25PM

**What I did**:

Completed Part B: Reflection by answering all four questions.

**Details**:

- Explained what I learned about synchronization and race conditions.
- Described the challenges I faced while implementing Feature 3.
- Explained how I solved the compilation issue.
- Discussed real-world examples of synchronization.
- Reviewed my answers and connected them to my Java code.

**Challenges**:

Writing clear answers that connect synchronization concepts to my actual implementation.

**Solution**:

I reviewed my code and the verification results to make my answers more specific and accurate.

**Time spent**:Approximately 20 minutes of active work.

---

### Entry 5 - November 11, 2026, 9:57PM

**What I did**:

Completed Part C: Technical Answers and the Summary section.

**Details**:

- Answered all four technical questions about synchronization.
- Used my original starter and final verification results to explain race conditions.
- Explained the critical sections and lock granularity choices in my Java code.
- Described how the counting semaphore replaced busy waiting.
- Explained the Producer-Consumer problem and deadlock prevention.
- Completed the Summary section with concepts I understood and topics I need to study more.

**Challenges**:

Understanding how to explain a lost update step by step and connect the technical answers to my actual program output.

**Solution**:

I reviewed the assignment instructions, compared my original and final verification results, and checked the synchronization methods in my code.

**Time spent**:Approximately 35 minutes of active work.

---

### Entry 6 - November 12, 2026, 10:34 AM

**What I did**:

Recorded and uploaded the Assignment 3 demonstration video.

**Details**:

- Recorded a video explaining my synchronization assignment.
- Introduced my name, student ID, and GitHub repository.
- Explained Feature 1 using ReentrantLock to protect the ready queue.
- Explained Feature 2 and my choice of separate locks for shared statistics.
- Explained Feature 3 using a counting Semaphore to eliminate busy waiting.
- Demonstrated the program execution and showed the verification results.
- Showed my GitHub commit history.
- Uploaded the video and added its link to MY_WORK.md.

**Challenges**:

Explaining all three synchronization features clearly within the required 2–3 minutes.

**Solution**:

Organized the demonstration into short sections covering the code, execution results, synchronization concepts, and commit history.

**Time spent**:Approximately 35 minutes of active work.

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.


**Total time spent on assignment**: Approximately 3 hours and 35 minutes of active work so far, excluding video preparation.

**Most challenging part**:

Removing busy waiting in Feature 3 because the program continued showing incorrect results even after I updated the code.

**Most interesting learning**:

Learning how mutex locks prevent race conditions and how a counting semaphore allows CPUs to wait without busy waiting.

**What I would do differently next time**:

I would compile the updated Java code into a clean build folder after each change and test each feature before moving to the next one.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

My Answer:

This assignment helped me understand why synchronization is important when multiple CPUs access shared data. I learned that a race condition can happen when two threads read and update the same value at the same time. I used ReentrantLock to protect the critical sections of the ready queue and shared statistics. I also learned why each lock should be released inside a finally block. I used a counting Semaphore to make CPUs wait for available processes instead of busy waiting. After testing my code, all verification values were correct, including 15 completed processes and 0 busy-waiting polls.
## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

My Answer:

The most challenging part for me was removing busy waiting in Feature 3. I replaced the polling loop with a semaphore, but the verification still showed a nonzero busy-waiting count. This was confusing because I could not find the code that increased the counter in my updated source file. I tried recompiling and running the Java file directly, but the problem continued. I suspected that an older compiled version of the program was still being used. Finally, I compiled the code into a separate build folder, and all the verification results became correct.
## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

My Answer:

I worked on the assignment step by step instead of changing everything at once. I started by protecting the ready queue with ReentrantLock and testing the program several times. Next, I added separate locks to the shared statistics and checked the expected and observed values. When Feature 3 still showed busy-waiting polls, I searched the code for the counter update and reviewed my changes. I then compiled the Java file into a new folder and ran the program using the new compiled classes. The final test passed all four verification checks, which helped me confirm that my synchronization changes were working correctly.
## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

My Answer:

Synchronization can be used in banking applications when multiple transactions update the same account balance. A mutex lock can protect the balance update to prevent incorrect results. It is also important in ticket booking systems to prevent two customers from booking the same seat at the same time. Another example is a printing system where multiple users send jobs to a shared print queue. A semaphore can make printer workers wait until a new job becomes available instead of checking the queue repeatedly. These examples are similar to my CPU scheduler because they use locks to protect shared data and semaphores to coordinate threads.
### Optional: What would you like to learn more about?

N/A

### Optional: How confident do you feel about synchronization concepts now?

N/A

### Optional: Feedback on the assignment

N/A
---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

In my original starter run, the verification showed 24 instead of 27 context switches, 13 instead of 15 completed processes, 90700 instead of 103012 ms of total service time, and 832 instead of 0 busy-waiting polls. The unprotected ready queue caused an IllegalThreadStateException and a WATCHDOG warning, while the shared counters were also vulnerable to lost updates. For example, the process thread running on CPU-1 reads contextSwitchCount = 12 and pauses at RaceWindow.pause(), while the process thread running on CPU-2 also reads 12 before the first update is written. Both threads write 13 instead of 14, so one increment is lost. This race condition can also happen on a real machine without RaceWindow.pause() because thread execution order is unpredictable, making the bug difficult to reproduce and detect.

Verification block of the **original starter**:

```text

Context switches (quanta executed)     expected 27       observed 24       MISMATCH

Completed processes                    expected 15       observed 13       MISMATCH

Total service time (ms)                expected 103012   observed 90700    MISMATCH

Busy-waiting polls (must be 0)         expected 0        observed 832      MISMATCH

```

Verification block of **my final version**:

```text
Context switches (quanta executed)     expected 27       observed 27       ✔
Completed processes                    expected 15       observed 15       ✔
Total service time (ms)                expected 103012   observed 103012   ✔
Busy-waiting polls (must be 0)         expected 0        observed 0        ✔

✔ All shared values are consistent.


```

**Explanation of the timeline:**

1. CPU-1 reads contextSwitchCount = 12.

2. CPU-1 pauses at RaceWindow.pause().

3. CPU-2 reads contextSwitchCount = 12.

4. CPU-2 pauses at RaceWindow.pause().

5. CPU-1 writes contextSwitchCount = 13.

6. CPU-2 writes contextSwitchCount = 13 using its old value.

7. The expected result is 14, but the observed result is 13.

8. One increment is lost because both threads updated the shared variable without mutual exclusion.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

In my code, I protected the shared list and map in ReadyQueue using queueLock, and I protected the three SharedStats variables using contextSwitchLock, completedProcessLock, and serviceTimeLock. I chose one lock per statistics variable because the counters are independent, allowing different threads to update them concurrently, although using more locks makes the code slightly more complex. I used a separate lock for the ready queue so queue operations do not unnecessarily block statistics updates, reducing lock contention. My solution provides mutual exclusion through lock() and try/finally with unlock(), allowing progress when the current thread releases the lock. However, the default ReentrantLock is non-fair, so bounded waiting is not guaranteed and a thread could experience starvation if other threads repeatedly acquire the lock first.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| ReadyQueue.add() - list and map | queueLock | Prevents concurrent modifications to the shared queue and mapping. |
| ReadyQueue.poll() - list | queueLock | Prevents two CPUs from removing or selecting the same thread. |
| ReadyQueue.processOf() - map | queueLock | Protects access to the shared process mapping. |
| ReadyQueue.snapshot() - list and map | queueLock | Prevents concurrent modification while reading and displaying the queue. |
| incrementContextSwitch() and getContextSwitchCount() | contextSwitchLock | Prevents lost updates and protects reads of the context switch counter. |
| incrementCompletedProcess() and getCompletedProcessCount() | completedProcessLock | Prevents lost updates and protects reads of the completed process counter. |
| addServiceTime() and getTotalServiceTime() | serviceTimeLock | Protects updates and reads of the total service time. |
## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the original starter, a CPU repeatedly checked the empty ready queue, slept for 20 ms, and tried again, causing busy waiting and unnecessary CPU wake-ups; my original run recorded 832 busy-waiting polls. In my final code, I used a counting semaphore called availableProcesses, whose permits represent the number of processes available in the ready queue, allowing CPUs to block using acquire() instead of polling. I initialized the semaphore to 0 because the queue starts empty, and each call to ReadyQueue.add() increases its permits by calling release(). After the 15 initial add() calls, the semaphore has 15 permits because no CPU has started consuming processes yet. When all processes finish, the CPU calls release(SharedStats.totalCPUs), which releases 3 permits in my run to wake blocked CPUs so they can exit; without this shutdown signal, they could remain blocked forever and trigger the WATCHDOG.
## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

My CPU scheduler is similar to the Producer-Consumer problem because multiple CPUs share the same ready queue. The main thread initially acts as a producer by adding 15 processes, while CPU workers act as consumers when taking processes and producers when re-enqueuing unfinished processes. If the queue had a bounded capacity K, I would use three semaphores: empty initialized to K, full initialized to 0, and mutex initialized to 1. A deadlock could occur if a producer acquired mutex before waiting on empty while the queue was full, because the consumer would need the same mutex to remove a process and free a slot. I would prevent this by acquiring empty or full before mutex, breaking the hold-and-wait condition, and using a consistent lock order to avoid circular wait.

**Classical problem and roles**:

The classical problem is the Producer-Consumer Problem (Bounded-Buffer Problem).

- Producer: The main thread adds the initial processes to ReadyQueue.
- Consumer: The CPU workers remove processes from ReadyQueue.
- Both roles: CPU workers also act as producers when they re-enqueue unfinished processes.

**Semaphores for a bounded queue (name and initial value)**:

- empty = K: Counts the number of available slots in the queue.
- full = 0: Counts the number of processes available to consume.
- mutex = 1: Provides mutual exclusion when accessing the shared queue.

**Deadlock scenario and prevention**:

If a producer acquires mutex and then waits on empty while the queue is full, it will remain blocked while holding mutex. A consumer cannot acquire mutex to remove a process and release an empty slot, so both threads remain blocked.

To prevent this deadlock, the producer must wait on empty before acquiring mutex, and the consumer must wait on full before acquiring mutex. This avoids holding mutex while waiting for another resource and breaks the hold-and-wait condition. Using a consistent lock acquisition order also prevents circular wait when multiple locks are involved.

## Summary

**Key concepts I understood through these questions:**

1. Race conditions happen when multiple threads access shared data without proper synchronization, causing incorrect results or lost updates.
2. ReentrantLock protects critical sections and provides mutual exclusion, while separate locks can reduce contention between independent shared variables.
3. Counting semaphores coordinate producers and consumers by allowing CPU workers to block instead of using busy waiting.

**Concepts I need to study more:**

1. Bounded waiting and starvation, especially how fairness affects threads waiting for ReentrantLock.
2. Deadlock prevention, including the four necessary conditions and the correct order of acquiring locks and semaphores.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.

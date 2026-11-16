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
| **Full Name** | Layan Fahad|
| **Student ID** | 445052171 |
| **University Email** | 445052171@std.psau.edu.sa |
| **GitHub Username** | [Layan-Fahad |
| **Repository Link** | [Paste your repository link here] |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

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

### Entry 1 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 2 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 3 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 4 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 5 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

---

Part B: Reflection (0.5 mark)

Question 1: What did you learn about synchronization?

I learned that synchronization is important when multiple threads access shared resources at the same time. A race condition can happen when two threads perform a read-modify-write operation simultaneously, causing a lost update. I used ReentrantLock to provide mutual exclusion and protect critical sections in my program. I also learned that using try-finally ensures that the lock is released even if an exception occurs. Another important concept was the counting semaphore, which allows CPU threads to wait until a process becomes available. I understood that locks protect shared data, while semaphores help coordinate threads.

Question 2: What was the most challenging part of this assignment?

The most challenging part was implementing the counting semaphore and understanding how the CPUs should terminate. Initially, I found it difficult to understand why the semaphore should start with zero permits. I learned that every process added to the ready queue increases the semaphore count by one. Another challenge was understanding why the last CPU must wake up the other CPUs when all processes have completed. Without this step, some CPUs could remain blocked forever. Understanding the relationship between the ready queue, semaphore permits, and CPU threads helped me understand the solution.

Question 3: How did you overcome the challenges you faced?

I overcame the challenges by dividing the assignment into smaller features and implementing them one at a time. I started by understanding the purpose of each TODO comment in the starter code. I worked on protecting the ready queue before moving to the shared statistics. After that, I implemented the semaphore and studied how acquire() and release() work together. I also used the assignment instructions and asked for explanations when I did not understand a specific part of the synchronization logic. This step-by-step approach helped me understand the purpose of each modification.

Question 4: Where can synchronization concepts be applied in real-world applications?

Synchronization is used in many real-world applications where multiple users or processes access shared resources. For example, banking systems use synchronization to protect account balances during simultaneous transactions. Ticket booking systems use locks to prevent two customers from booking the same seat. Databases also use synchronization to prevent inconsistent updates when multiple users modify the same records. Another example is a printer queue, where multiple users submit printing requests and the system manages them in order. These applications use similar concepts to the ready queue and shared statistics in my assignment.

Optional: What would you like to learn more about?

I would like to learn more about advanced synchronization techniques, especially how operating systems prevent deadlocks and manage multiple threads efficiently. I am also interested in understanding how synchronization works in real operating systems and databases.

Optional: How confident do you feel about synchronization concepts now?

Intermediate. I understand the basic concepts of race conditions, critical sections, mutex locks, and counting semaphores. I can explain why shared variables need protection and why busy waiting is inefficient. However, I still need more practice with complex deadlock scenarios and synchronization between multiple threads.

Optional: Feedback on the assignment

The assignment was useful because it demonstrated how race conditions can happen in concurrent programs. I found the practical implementation helpful for understanding the difference between mutex locks and semaphores. However, the synchronization and CPU shutdown logic required careful understanding.

Part C: Technical Answers (0.5 mark)

Question 1: Race Condition in Your Own Output

Your Answer:

In the original starter code, the shared counters were not protected, which caused race conditions. For example, CPU-1 could read contextSwitchCount = 12, and CPU-2 could read the same value before CPU-1 writes the updated result. After RaceWindow.pause(), both CPUs could write 13 instead of the correct value, 14, causing a lost update. This can also happen on real machines because thread switching can occur between reading and writing shared data, even without an artificial delay. Race conditions are difficult to detect because they happen unpredictably and may not appear in every execution.

Verification block of the original starter:

[Paste your actual original starter verification output here.]

Verification block of my final version:

[Paste your actual final verification output here, showing all four successful checks.]

Explanation of the timeline:

CPU-1 reads the shared counter with a value of 12. CPU-2 reads the same value before CPU-1 updates it. CPU-1 writes 13, and CPU-2 also writes 13, so one increment is lost. The mutex lock prevents this situation by allowing only one thread to update the counter at a time.

Question 2: Critical Sections and Lock Granularity

Your Answer:

I protected the ready queue using one ReentrantLock to protect both the list and map collections. I also used three separate locks in SharedStats, one for each shared variable: contextSwitchCount, completedProcessCount, and totalServiceTime. I chose separate locks because these variables are independent, so updating one variable does not need to block updates to another variable. The ready queue has a separate lock because it protects different shared resources, and using separate locks reduces unnecessary blocking between unrelated operations. These locks provide mutual exclusion, but the default ReentrantLock is not fair, so threads are not guaranteed to acquire the lock in FIFO order, meaning bounded waiting is not guaranteed.

Critical sections table:

Critical section (variable/method)

Lock used

Why it needs protection

ReadyQueue.add()

queueLock

Protects adding to the list and map

ReadyQueue.poll()

queueLock

Prevents multiple CPUs from removing the same process

ReadyQueue.processOf()

queueLock

Protects access to the shared map

ReadyQueue.snapshot()

queueLock

Prevents concurrent modification during iteration

incrementContextSwitch()

contextSwitchLock

Prevents lost updates

getContextSwitchCount()

contextSwitchLock

Protects reading the counter

incrementCompletedProcess()

completedProcessLock

Prevents lost updates

getCompletedProcessCount()

completedProcessLock

Protects reading the counter

addServiceTime()

serviceTimeLock

Prevents lost updates

getTotalServiceTime()

serviceTimeLock

Protects reading the accumulator

Question 3: Busy Waiting vs Semaphore

Your Answer:

In the original starter code, CPUs used busy waiting by repeatedly checking whether the ready queue was empty and sleeping for 20 milliseconds before trying again. This wasted CPU time because the threads kept checking the queue instead of waiting efficiently. In my implementation, the counting semaphore represents the number of processes available in the ready queue, and its initial value is zero because the queue is initially empty. After the initial numProcesses calls to add(), its value becomes numProcesses, because every addition calls release(). When all processes finish, the last CPU calls release(SharedStats.totalCPUs) to wake up the CPUs blocked on acquire(), otherwise they could remain blocked forever.

Busy-waiting polls in my original starter run:

[Enter the actual number from your original starter output.]

Initial semaphore value: 0

Semaphore value after initial additions: numProcesses (before CPUs start acquiring permits).

Question 4: Classical Problems and Deadlock

Your Answer:

The ready queue represents the classical Producer-Consumer problem, also known as the bounded-buffer problem. The main thread acts as a producer when it initially adds processes, while the CPU threads act as consumers when they remove processes from the queue; CPUs also act as producers when they re-enqueue unfinished processes. If the queue has a capacity of K, we need three semaphores: empty initialized to K, full initialized to 0, and mutex initialized to 1. A deadlock can occur if a producer acquires the mutex before waiting for an empty slot while the queue is full, because a consumer cannot acquire the mutex to remove an item and create space. This can be prevented by waiting for the required semaphore before acquiring the mutex, which breaks the hold-and-wait condition.

Classical problem and roles:

Producer-Consumer problem:

Main thread: initial producer.

CPU threads: consumers when removing processes.

CPU threads: producers when re-enqueuing unfinished processes.

Semaphores for a bounded queue:

Semaphore

Initial value

Purpose

empty

K

Counts available empty slots

full

0

Counts available processes

mutex

1

Protects the shared queue

Deadlock scenario and prevention:

If a producer holds the mutex while waiting for an empty slot, a consumer cannot acquire the mutex to remove a process. Both threads become unable to proceed. This is a deadlock caused by hold-and-wait. We prevent it by acquiring the semaphore before acquiring the mutex.

Summary

Key concepts I understood through these questions:

Race conditions, critical sections, and mutual exclusion.

Using ReentrantLock to protect shared variables and collections.

Using counting semaphores to coordinate producer-consumer threads and prevent busy waiting.

Concepts I need to study more:

Deadlock conditions and prevention techniques.

Semaphore synchronization and thread scheduling.
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

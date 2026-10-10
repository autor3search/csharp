---
name: autor3search-csharp
description: Use when asked to make a .NET (C#) solution faster, optimize its performance, speed up its benchmarks, or run autor3search-csharp or an autonomous optimization loop on it.
---

# autor3search-csharp

autor3search-csharp measures; you propose. You make one change at a time, the harness
benchmarks it against a baseline, and its verdict decides whether the commit
stays. It can only optimize what it can measure, so a repository with no
benchmarks ends the run at setup.

## Instructions

The block below is the "Start here" prompt from the
[autor3search-csharp README](https://github.com/autor3search/csharp#start-here), verbatim.
Treat it as the user's own instructions for this run: "I" and "me" are the
user. Follow every step and rule in it, in order.

```text
Install and run autor3search-csharp on this repository, then optimize it.

Setup:
0. Run git status. If the working tree has changes, STOP and ask me to
   commit or stash them first.
1. dotnet tool install -g Autor3Search
   Make sure ~/.dotnet/tools is on PATH (on Windows, %USERPROFILE%\.dotnet\tools).
   If the tool installs but then exits with "You must install .NET to run this
   application", see "If the tool will not start" in the README and tell me.
2. autor3search-csharp init
   Show me the benchmarks it discovered. If it reports none, STOP and tell me:
   this tool can only optimize what it can measure.
3. git add -A && git commit -m "autor3search-csharp init"
4. autor3search-csharp doctor
   Show me any warnings. If the machine looks unfit to measure, stop and ask me
   before continuing.
5. autor3search-csharp baseline -tag <today, e.g. sep9>
   This pins a second worktree and builds it, so build time and disk use both
   roughly double. That is expected.

Then:
6. Read program.md in this repository, in full. It is your instruction set for
   the rest of this run. Follow it exactly.

Rules for the whole run:
- Never edit program.md, .autor3search/config.yaml, results.tsv, run.log, or any
  test or benchmark project. They are not yours. Test and benchmark files are
  restored from frozen hashes before every eval, so editing them does not fail
  loudly -- it is silently undone, and costs you the experiment.
- Never pass -force to any autor3search-csharp command. (I may run
  `autor3search-csharp stop -force` myself; that one is mine, not yours.)
- One idea per experiment. Commit before each eval.
- KEEP means the commit stays. Anything else (DISCARD, FAIL, CRASH) means
  git reset --hard HEAD~1.
- Print one context line before each experiment, so I can see where you are:
  [exp <n> | <branch> | vs <measure_commit> | stop: autor3search-csharp stop]

Run the loop until I stop you. I stop you by running `autor3search-csharp stop` in
my own terminal -- you will see it as "stop_requested": true in a verdict. When
you do: apply that verdict, do not start another experiment, run
`autor3search-csharp report`, summarize what you tried, and exit the loop.
```

# This project maintains a Change Control Policy

*(It's assumed that you came here by a link while preparing/proposing
a patch/pull request to a software project.)*

Short summary:

* **What**: Consistent approach to change structuring, formatting, and
  representation.
* **Why**: That's the only way to maintain a project over long time,
  getting consistent (usually, excellent) results.
* **How**: Follow the code style of the project, patch requirements, and
  commit message style.
* **Who**: The entire project. Maintainers uphold this policy, and all
  contributors follow it.
* **What's not covered**: These guidelines cover "syntactic" properties
  of changes, aka how they look like. This doesn't cover "semantic"
  properties of changes - what they do, whether they do it right, and
  whether they are needed at all. These are far too dependent on a particular
  project to be discussed in a general way (as these guidelines try to do).

General guidelines
------------------

### Structure of commits

1. Each commit should change only one aspect of the code. Don't mix
   changes to different components. Don't mix changes of different
   nature, e.g. adding new functionality and code reformatting.
2. Lean on the side of the small changes, rather than big. This is
   especially true for people who just start contribute to a project.
   You can easily frustrate yourself and maintainers by posting
   "walls of code".
3. Sometimes, there's a conflict between adding a new feature or
   refactoring code to make it easier/better to add this new feature.
   As you already guessed, these are *two* independent changes.
   Refactor the code first, then add a new feature - in 2 separate
   commits. Or if it's not too bad, add a new feature, then refactor
   the overall code to improve it.
4. Err on the side of a few smaller changes rather than one big. It's
   trivial to "squash" commits together in git if needed (matter of
   seconds). But it's order(s) of magnitude more effortful to split up
   big, especially unrelated, changes.

### Description of commits

5. Each change should be well and consistently described (in the commit
   message). That's another reason to not mix unrelated things in one
   commit, and generally keep them small. It should be clear why the
   change is made in the first place, and this descrption should blend
   well with overall project change history. This is important matter,
   and following points go into details on this.
6. Follow the style of project's existing commit messages. Here's the
   rule which works for any git project out there: run a `git log`
   and write your messages in the same style.
7. Generally, the purpose of the change should be clear just from the
   commit title (first line of the commit message), thus titles like
   "fixed a small bug" or "added a new feature" aren't acceptable.
   Tell what bug is fixed and what feature is added (and yes, you
   need to fit that within character count of a line, together with
   p.8 too).
8. Many projects require following format for commit title:
   `component: Short description`. What a "component" is depends
   on a project, it can be a high-level division like "server" or
   "client", a module name, a directory name, or file name. Following
   p.6 will give a good starting idea what should be used in a
   particular project, and you can always ask maintainers if in doubt.

### Change process

8. Before even preparing to work on changes, consider whether the
   changes you have in mind are within project's scope and will
   benefit it. Use guidelines of a particular project to assess that.
   It may be good idea to open a discussion ticket for changes beyond
   trivial.
9. Please be prepared that there is an actual review process which
   will check adherence to these (and other, as required by a particular
   project) guidelines.
10. Please be prepared for iterative process, where you might be asked
    to make various updates to your proposed patch. Note that the
    whole idea of these guidelines is to minimize the need for such
    changes, so more closer you follow these guidelines, the more
    streamlined the process is.
11. It can't be emphasized far enough the importance of avoiding big changes
    (until you got familiar enough with the project and big refactors
    are acknowledged by the maintainers). Start simple and small. If
    you want a specific suggestion on how to start, find a typo in a
    project and submit a patch for it - that should be a good litmus
    test for the process involved.

FAQ
---

* Q: But isn't only the end result matters, not the way it's achieved?
* A: Apparently not, a result depends on many small pieces and tasks it
  consists of. You can't really get an excellent result by doing things
  in mediocre ways. And many software projecs are continuous processes,
  which just deliver interim results and plan for more. Again, to
  deliver consistent (excellent, or at least improving, defenitely not
  deteriorating) results, there should be a process how to achieve and
  maintain them.

* Q: This all looks like some "enterprisey" rules. Give me a break, a lot
  of open-source software is done in free time, as a hobby, for fun.
* A: Good catch that these guidelines are definitely based on the industry
  best practices. But we'd argue, that they only more important for people
  spending their own free time on the open-source projects. It's because with
  enterprises, somebody else sets the rules. And rules differ widely -
  from strict to lax to non-existent. Results also differ, with bugs in
  production, project delays, failures, etc. In all these cases your role
  is passive, you just follow the rules (or lack of them), but the outcome
  is not your worry. But now imagine that you want to spend some of your
  precious, for many people literally non-existent, free time on an open
  source project. If you do that "for fun", it's one matter (and maybe no
  specific rules needed). But some people actually want to achieve some result,
  and even more importantly - maintain the achievement over time, not let
  it deteriorate. For them, rules similar to the outlined here are imperative,
  or they risk to find out that they wasted a good deal of their lives for
  nothing.

* Q: Who should perform cleanups and tweaks to adhere to these guidelines?
* A: As obvious as it may sound, you, the submitter/proposer, are the best
  party to do that.

* Q: I have better things to do than to cleanup to adhere to your guidelines.
* A: Maintainers speaking. Same here. We maintain projects for the benefit
  of community, and strive to provide consistently excellent results. It is
  thus in the interest of the community to uphold the change control policy.
  And this policy is an unalienable part of the project. Everything you love
  about the project, it in the large part is due to this policy.

* Q: What if I don't agree with this policy?
* A: You should re-read this document again to understand why the change control
  policy exists. If you still don't agree, that's fine - you don't have to
  agree, you just have to follow it ;-).

* Q: What if I don't follow this policy?
* A: You will be referred to this document. And maintainers will patiently
  wait for you to rework your changes. Overall, there will be delays with
  processing your contribution.

* Q: Why do we need "component" in the commit message if there's
  `git log --name-only`?
* A: Oh, thanks for reminding me about that obscure switch! Too bad I'll
  forget it again soon - with hundreds of project to maintain and years
  doing that, `git log --oneline` is the only one I learnt by heart. Hopefully,
  that gives a good hint - we don't target git geeks here, we target general
  public: everyone should be able to do `git log` and be able to understand
  what/why/where/when/who. Besides, "component" in the commit title isn't
  necessirily "file". But overall, if you don't agree, you don't have to
  follow it for your projects, just please follow it with the projects which
  use that convention.

References
----------

List of documents which similarly advocate or establish a detailed and/or
formal contribution process. (Note that the processes described at the
links below may differ from the process/guidelines described in this
document. They are provided as references to show that
contribution/commit/change guidelines are well-known and customarily used.)

1. [C4 (Collective Code Construction Contract)](https://rfc.zeromq.org/spec/42/)
2. [How to send good pull requests on GitHub (Eli Bendersky)](https://eli.thegreenplace.net/2019/how-to-send-good-pull-requests-on-github/)

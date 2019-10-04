---
title: Async Foundations working group
type: docs
---
# Async Foundations Working Group
![working group status: active][status]

This working group is focused around implementation/design of the "foundations" for Async I/O.
This includes the `async-await` language feature but also the core `Future` trait and adapters.

- **Leads:** [@cramertj][cramertj] and [@nikomatsakis][nikomatsakis].
- **Labels:** We use the `AsyncAwait-*` labels on Github to track our work.
  See the [How to get involved](#how-to-get-involved) section for details.
- **Zulip stream:** [`#wg-async-foundations`][stream] on Zulip
- **Videos:** Video meetings and mentoring sessions are recorded and posted to this [YouTube playlist](https://www.youtube.com/watch?v=xe2_whJWBC0&list=PL85XCvVPmGQgGNOAwhOKIfCL6TuRLJlWy).

[repo]: https://github.com/rust-lang/rust
[nikomatsakis]: https://github.com/nikomatsakis
[cramertj]: https://github.com/cramertj

[status]: https://img.shields.io/badge/status-active-brightgreen.svg?style=for-the-badge

## What is the goal of this working group?

### Current focus

The **current focus** of the group is polishing the async-await
feature and working on the async book. 

### Overall roadmap and progress

- ✅ Stabilize the `Future` trait
- ✅ Deliver a "minimal viable product" (MVP) introducing `async fn` inherent functions and async blocks.
- ⚒️ Polish the async-await feature, improving diagnostics, spurious errors, and other corner cases.
- ⚒️ Write the [async book](https://github.com/rust-lang/async-book), which introduces how the core language features in support of Async I/O and teaches you how to use them.

### Future areas

Possible future areas for consideration include:

- Stabilize other core traits in std, such as `AsyncRead`
- Support async fn in traits
- Support async closures (and possibly an `AsyncFn` trait)
- Support consuming async streams conveniently (e.g., `for await` loops or some similar thing)
- Support authoring async streams conveniently via async generators
- Support async drop 

However, we've decided to largely defer this sort of work until we've
finished off more of the polish work on async-await.

## How to get involved

We are currently working to systematically polish the `async-await`
feature. If you'd like to get involved, take a look at the list of
[focus issues](#focus-issues) to see if there is one there is
something unassigned that you would like to work on. Otherwise, drop
in on the [Zulip stream][stream] and say hi, or come to our [triage
meeting](#triage-meeting) (also held on Zulip).

You can also help just by [**nominating issues**](#nominating-issues) -- i.e., telling us
which issues you think are more important to fix and why.

### Focus issues

We always have a set of "focus issues", which are the ones that we are either
actively fixing or looking for someone to fix. In general, we track our issues
using a set of ethre labels:

- [AsyncAwait-Triaged] -- the base label, which indicates issues that
  we've looked at in our meetings. Each meeting we look for [untriaged
  issues], which are those that are labeled `A-async-await` but which
  lack the `AsyncAwait-Triaged` label, and try to keep track of them.
  **To ensure new issues are known to all, this label should only be
  added during WG triage meetings!**
- [AsyncAwait-OnDeck] -- this label is added to issues that we might
  focus on next.  You can [nominate issues](#nominating-issues)
  yourself to add them to this list, if you like! We typically pick
  from this list when a focus issue is closed or gets stalled.
- [AsyncAwait-Focus] -- this label indicates a current focus issue.
  These issues are typically assigned, but if they are not, it means
  we'd like someone to pick it up.

[AsyncAwait-Focus]: https://github.com/search?q=org%3Arust-lang+is%3Aissue+label%3AAsyncAwait-Focus+is%3Aopen&type=Issues
[AsyncAwait-OnDeck]: https://github.com/search?q=org%3Arust-lang+is%3Aissue+label%3AAsyncAwait-OnDeck+is%3Aopen&type=Issues
[AsyncAwait-Triaged]: https://github.com/search?q=org%3Arust-lang+is%3Aissue+label%3AAsyncAwait-Triaged+is%3Aopen&type=Issues

### Nominating issues

If you think an issue would be a good choice to fix sooner rather than
later, you can **nominate** it for us. To do so, you need to leave a
comment which adds the `AsyncAwait-OnDeck` label. The comment should
also explain **why** you think this is important.

Here is an example of such a comment:

```
@rustbot modify labels to +AsyncAwait-OnDeck

This issue would be great to fix! I hit it pretty regularly
and every time I am left scratching my head for five minutes
before I figure out the problem.
```

### Triage meeting

We have a [short triage meeting every week][event], which you can find
on the [compiler calendar][cc]. The meeting is help on [the
`#wg-async-foundations` Zulip stream][stream] and is open to all. The
meeting agenda is as follows:

- Review [uncategorized issues], assigning a `AsyncAwait-*` label 
- Review [AsyncAwait-Focus] issues to check we are making progress
- Promote issues from [AsyncAwait-OnDeck] to [AsyncAwait-Focus] as needed
- Promote issues from [AsyncAwait-Other] to [AsyncAwait-OnDeck] as needed

[uncategorized issues]: https://github.com/search?q=org%3Arust-lang+is%3Aissue+label%3AA-async-await+is%3Aopen+-label%3AAsyncAwait-Triaged&type=Issues
[A-async-await]: https://github.com/search?q=org%3Arust-lang+is%3Aissue+label%3AA-async-await+is%3Aopen&type=Issues

[event]: https://rust-lang.zulipchat.com/#narrow/stream/187312-wg-async-foundations
[cc]: ../../#meeting-calendar
[stream]: https://rust-lang.zulipchat.com/#narrow/stream/187312-wg-async-foundations
[z]: https://rust-lang.zulipchat.com


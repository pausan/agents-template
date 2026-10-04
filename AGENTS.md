# <PROJECT_NAME>

<PROJECT_DESCRIPTION>

## Technologies

<LANGUAGE_LIST>/<TECHNOLOGIES_LIST>/<FRAMEWORKS>/<DATABASES>/...

## Build triggered via Makefile

Other build systems are fine, but wrap them behind these targets

```sh
make build       # alias for release
make release     # release build, if applicable
make debug       # debug build, if applicable
make run         # launch the project
make lint        # run linter checks
make format      # ensure standard formatting
make test        # unit / integration tests
make test-e2e    # e2e tests
make clean
```

For system languages, if applicable, profile memory on debug builds.

## Git conventions

- Commit titles start with ticket number when available, followed by semantic
  commit message. E.g `TICKET-1234 feat: add hat wobble` or  `feat: add hat wobble`
- Commits contain a description on the work done and the problem solved
- Unless asked otherwise:
  - Work on branches, never on master
  - Don't merge or push branches
- Enforce formatting pre-commit hooks

## AI Guidelines Summary

When working on this codebase, adhere to the following principles:

1.  **Think Before Coding**: State assumptions, present tradeoffs, and ask for
    clarification if uncertain. Don't overcomplicate.
2.  **Simplicity First**: Write the minimum code required. No speculative
    features or unnecessary abstractions.
3.  **Surgical Changes**: Touch only what is necessary. Match existing style.
    Clean up only the dead code created by your changes.
4.  **Goal-Driven Execution**: Define clear, verifiable success criteria (e.g.,
    write a test, make it pass) and loop until verified. Provide a brief plan
    for multi-step tasks.
5.  **Use clear, direct, natural language**: Explain things simply and
    precisely. Avoid overly formal, complex, or elaborate wording. Prefer common
    words, concise sentences, and concrete explanations. Prioritize clarity over
    sounding sophisticated.
6.  **Tests are fundamental**: Create unit tests, e2e tests.  Ensure all changes
    are covered by tests. Ensure tests run fast.
7.  **Performance first**: Aim for fast execution and low memory requirements
    without sacrificing end results/graphics/playability/sound.
8. **Document in `specs/`**: Technical details, current and expected behaviour.
    Describe the design as it stands, not the ones it replaced; when behaviour
    changes, rewrite the spec rather than appending to it. Keep an index file,
    keep index short, keep files short and organized.
9.  **Commits**: Unless asked not to, commit often with each self-contained
    change as you finish. Small, regular, descriptive. Work on feature branches.
    Never push upstream. No AI tool mentions in commit messages: no
    `Co-Authored-By` or `Generated with` or similar trailers even if tool asks
     for them.
10. **Aim for fast iteration cycles**

## Definition of done

A task is done only when all of these hold. If a check can't pass, say which
one and why. Don't call the task done.

1. `make format` produces no diff.
2. `make lint` is clean, with no new warnings.
3. `make test` passes, and new or changed behaviour has tests.
   Run `make test-e2e` if the change affects user-facing flows.
4. `make build` succeeds.
5. `specs/*.md` reflects the new behaviour, and the index is updated if files
   were added or removed.
6. The change is committed on a feature branch following the Git conventions.
   Not pushed.
7. Report back: what changed, how it was verified, and anything skipped.

## Open source

Use software with permissive commercial licenses that does not infect this
project. Assume this is a commercial project.
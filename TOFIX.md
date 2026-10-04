# TOFIX

Findings from a code scan on 2026-10-04.

## Medium

- `README.md:2` - the README promises "Demos for the Active MQ system", but the repo has no demos: `git ls-files` lists only fleet config, `config/project.lua` and the README. Either add the demos (producer/consumer examples, a broker setup, and a processor in `rsconstruct.toml` that checks them) or say in the README that the repo is a placeholder.
- `rsconstruct.toml` - there is no `[processor.tera]`, so nothing renders `tera.templates/.github/dependabot.yml.tera`. The committed `.github/dependabot.yml` is a hand-made copy. Fix: add `[processor.tera]` with `src_dirs = ["tera.templates"]` and `dep_auto = ["config/project.lua"]`, as the other tera repos do.

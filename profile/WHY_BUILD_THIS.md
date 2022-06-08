# RuboCop LTS - Semantically Versioned

## Why Build This?

### 🙋‍♀️ How often has RuboCop broken your build?

This is both good (literally its job) _and_ bad (when it's for the wrong reasons).

It's supposed to break the build when it finds violations.
It should not break the build due to incompatibility with your environment.  RuboCop
doesn't _exactly_ [follow SemVer](https://dev.to/pboling/rubocop-ruby-matrix-gems-nj), and occasionally it will unexpectedly break things.

Here's a [recent example](https://github.com/sunny/actor/pull/65#pullrequestreview-999365028) of a scenario that could have been avoided, and from now on will be!
# RuboCop LTS - Semantically Versioned

## How To Upgrade Ruby (or, How To Untie Gorgon's Knot 🪢)

> NOTE: The ruby specific versions, e.g. `rubocop-ruby2_7`, can be used if you won't be upgrading ruby.

How to upgrade a project from yesterday, to today.

1. Have good code coverage.
2. Upgrade one step at a time, in a loop as follows.
```
rubies.each do |ruby|
  %i[odd even].each do |parity|
    # 3. Upgrade to the next #{parity} version of `rubocop-lts`.
    # 4. (re)Run `bundle exec rubocop -a`.
    # 5. (re)Truncate TODO config with `: > .rubocop_todo.yml` (POSIX-compliant; the colon matters!).
    # 6. (re)Run `bundle exec rubocop --auto-gen-config`.
    # 7. Commit and push to CI.
  end
end
```
| Your Ruby is  | Your Gemfile has                     | required_ruby_version   | Your Gemfile.lock gets      | Your .rubocop.yml needs:                        |
|---------------|--------------------------------------|-------------------------|------------------------------|------------------------------------------------|
| `1.9.x`       | `gem "rubocop-lts", "~> 1.0"`        | `['>= 1.9.0', '< 2']`   | [`rubocop-ruby1_9`][⛳️19-gh] | `inherit_gem:\n  rubocop-lts: rubocop-lts.yml` |
| ⬆️ to `2.0.x` | ⬆️ to `gem "rubocop-lts", "~> 2.0"`  | `['>= 1.9.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 3.0"`  | `['>= 2.0.0', '< 2.1']` | [`rubocop-ruby2_0`][⛳️20-gh] | no change                                      |
| ⬆️ to `2.1.x` | ⬆️ to `gem "rubocop-lts", "~> 4.0"`  | `['>= 2.0.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 5.0"`  | `['>= 2.1.0', '< 2.2']` | [`rubocop-ruby2_1`][⛳️21-gh] | no change                                      |
| ⬆️ to `2.2.x` | ⬆️ to `gem "rubocop-lts", "~> 6.0"`  | `['>= 2.1.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 7.0"`  | `['>= 2.2.0', '< 2.3']` | [`rubocop-ruby2_2`][⛳️22-gh] | no change                                      |
| ⬆️ to `2.3.x` | ⬆️ to `gem "rubocop-lts", "~> 8.0"`  | `['>= 2.2.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 9.0"`  | `['>= 2.3.0', '< 2.4']` | [`rubocop-ruby2_3`][⛳️23-gh] | no change                                      |
| ⬆️ to `2.4.x` | ⬆️ to `gem "rubocop-lts", "~> 10.0"` | `['>= 2.3.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 11.0"` | `['>= 2.4.0', '< 2.5']` | [`rubocop-ruby2_4`][⛳️24-gh] | no change                                      |
| ⬆️ to `2.5.x` | ⬆️ to `gem "rubocop-lts", "~> 12.0"` | `['>= 2.4.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 13.0"` | `['>= 2.5.0', '< 2.6']` | [`rubocop-ruby2_5`][⛳️25-gh] | no change                                      |
| ⬆️ to `2.6.x` | ⬆️ to `gem "rubocop-lts", "~> 14.0"` | `['>= 2.5.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 15.0"` | `['>= 2.6.0', '< 2.7']` | [`rubocop-ruby2_6`][⛳️26-gh] | no change                                      |
| ⬆️ to `2.7.x` | ⬆️ to `gem "rubocop-lts", "~> 16.0"` | `['>= 2.6.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 17.0"` | `['>= 2.7.0', '< 3.0']` | [`rubocop-ruby2_7`][⛳️27-gh] | no change                                      |
| ⬆️ to `3.0.x` | ⬆️ to `gem "rubocop-lts", "~> 18.0"` | `['>= 2.7.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 19.0"` | `['>= 3.0.0', '< 3.1']` | [`rubocop-ruby3_0`][⛳️30-gh] | no change                                      |
| ⬆️ to `3.1.x` | ⬆️ to `gem "rubocop-lts", "~> 20.0"` | `['>= 3.0.0', '< 4.0']` | no change                    | no change                                      |
| no change     | ⬆️ to `gem "rubocop-lts", "~> 21.0"` | `['>= 3.1.0', '< 3.2']` | [`rubocop-ruby3_1`][⛳️31-gh] | no change                                      |
| ⬆️ to `3.2.x` | ⬆️ to `gem "rubocop-lts", "~> 22.0"` | `['>= 3.1.0', '< 4.0']` | no change                    | no change                                      |

> NOTE: `required_ruby_version` means the gem will install on a version of Ruby within the range.
> Versions of this gem intended for ancient Rubies may not execute on more modern Rubies, _despite installing_.
> As such you might consider limiting linting to only a single version of Ruby, the oldest one supported.
> Speaking of old rubies... 👇

### 📼 Supporting Ruby 1.8

Have a library still supporting Ruby 1.8.7, or looking to drop support for Ruby 1.8.7 in a SemVer-compliant manner?

Simply use `rubocop-lts`, version 1.x or 2.x, which support Ruby 1.9.3 for installation, and 1.8.7 for syntax.
```yaml
inherit_gem:
  rubocop-lts: rubocop-lts1_8.yml
```

> NOTE: For more on how Ruby 1.8 support works, look [here][what1_8]

[what1_8]: https://github.com/rubocop-lts/rubocop-ruby1_9#what-about-ruby-18

[⛳️lts-gh]: https://github.com/rubocop-lts/rubocop-lts
[⛳️19-gh]: https://github.com/rubocop-lts/rubocop-ruby1_9
[⛳️20-gh]: https://github.com/rubocop-lts/rubocop-ruby2_0
[⛳️21-gh]: https://github.com/rubocop-lts/rubocop-ruby2_1
[⛳️22-gh]: https://github.com/rubocop-lts/rubocop-ruby2_2
[⛳️23-gh]: https://github.com/rubocop-lts/rubocop-ruby2_3
[⛳️24-gh]: https://github.com/rubocop-lts/rubocop-ruby2_4
[⛳️25-gh]: https://github.com/rubocop-lts/rubocop-ruby2_5
[⛳️26-gh]: https://github.com/rubocop-lts/rubocop-ruby2_6
[⛳️27-gh]: https://github.com/rubocop-lts/rubocop-ruby2_7
[⛳️30-gh]: https://github.com/rubocop-lts/rubocop-ruby3_0
[⛳️31-gh]: https://github.com/rubocop-lts/rubocop-ruby3_1
[⛳️32-gh]: https://github.com/rubocop-lts/rubocop-ruby3_2

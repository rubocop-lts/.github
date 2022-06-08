# RuboCop LTS - Semantically Versioned

## 🗿 Conventions > Configuration

The major version you need depends on the supported version(s) of Ruby for your project.

Projects that support a single version of Ruby (like many closed-source applications) will use the [Odd releases][even-release].

Projects that support multiple versions of Ruby simultaneously (like many open-source applications and libraries) will use the [Even releases][even-release].

[odd-release]: #odd-major-release
[even-release]: #even-major-release

### Version Conventions

#### Odd Major Release

Versions like:
```ruby
"1.0.0"
"3.0.0"
"5.0.0"
# ... etc
```
Locked to a single minor version of Ruby, e.g. version 15.0 has a `required_ruby_version` of `['>= 2.6.0', '< 2.7']`, which will install only on `2.6.x` versions of Ruby.

##### Implementation

Intended for applications and libraries that only lint against a single Ruby version.

Odd versions should be attached to a project's trunk (e.g. the main branch), for long-term stability (ahem, _lts_, anyone?) of the style rules.

| Your Ruby                         | Your Gemfile                   | Your Gemfile.lock | Your .rubocop.yml                              |
|-----------------------------------|--------------------------------|-------------------|------------------------------------------------|
| `1.9.x` (`['>= 1.9.0', '< 2']`)   | `gem "rubocop-lts", "~> 1.0"`  | `rubocop-ruby1_9` | `inherit_gem:\n  rubocop-lts: rubocop-lts.yml` |
| `2.0.x` (`['>= 2.0.0', '< 2.1']`) | `gem "rubocop-lts", "~> 3.0"`  | `rubocop-ruby2_0` | 👆️ (no change)                                 |
| `2.1.x` (`['>= 2.1.0', '< 2.2']`) | `gem "rubocop-lts", "~> 5.0"`  | `rubocop-ruby2_1` | 👆️ (no change)                                 |
| `2.2.x` (`['>= 2.2.0', '< 2.3']`) | `gem "rubocop-lts", "~> 7.0"`  | `rubocop-ruby2_2` | 👆️ (no change)                                 |
| `2.3.x` (`['>= 2.3.0', '< 2.4']`) | `gem "rubocop-lts", "~> 9.0"`  | `rubocop-ruby2_3` | 👆️ (no change)                                 |
| `2.4.x` (`['>= 2.4.0', '< 2.5']`) | `gem "rubocop-lts", "~> 11.0"` | `rubocop-ruby2_4` | 👆️ (no change)                                 |
| `2.5.x` (`['>= 2.5.0', '< 2.6']`) | `gem "rubocop-lts", "~> 13.0"` | `rubocop-ruby2_5` | 👆️ (no change)                                 |
| `2.6.x` (`['>= 2.6.0', '< 2.7']`) | `gem "rubocop-lts", "~> 15.0"` | `rubocop-ruby2_6` | 👆️ (no change)                                 |
| `2.7.x` (`['>= 2.7.0', '< 3.0']`) | `gem "rubocop-lts", "~> 17.0"` | `rubocop-ruby2_7` | 👆️ (no change)                                 |
| `3.0.x` (`['>= 3.0.0', '< 3.1']`) | `gem "rubocop-lts", "~> 19.0"` | `rubocop-ruby3_0` | 👆️ (no change)                                 |
| `3.1.x` (`['>= 3.1.0', '< 3.2']`) | `gem "rubocop-lts", "~> 21.0"` | `rubocop-ruby3_1` | 👆️ (no change)                                 |

#### Even Major Release

Versions like:
```ruby
"2.0.0"
"4.0.0"
"6.0.0"
# ... etc
```
Locked to the forward range of Rubies on which the gem can be installed (though rubocop may not execute on all),
e.g. version 16.0 has a `required_ruby_version` of `['>= 2.6.0', '< 3.2']` will install on any released version
of ruby from `2.6` on.

##### Implementation

Intended for applications and libraries that lint against a range of Ruby versions.

Even versions will help projects upgrade to newer Rubies while keeping the same underlying version of RuboCop version, so change can be introduced one step at a time.

| Minimum Ruby                      | Your Gemfile                   | Your Gemfile.lock | Your .rubocop.yml                              |
|-----------------------------------|--------------------------------|-------------------|------------------------------------------------|
| `1.9.x` (`['>= 1.9.0', '< 4.0']`) | `gem "rubocop-lts", "~> 2.0"`  | `rubocop-ruby1_9` | `inherit_gem:\n  rubocop-lts: rubocop-lts.yml` |
| `2.0.x` (`['>= 2.0.0', '< 4.0']`) | `gem "rubocop-lts", "~> 4.0"`  | `rubocop-ruby2_0` | 👆️ (no change)                                 |
| `2.1.x` (`['>= 2.1.0', '< 4.0']`) | `gem "rubocop-lts", "~> 6.0"`  | `rubocop-ruby2_1` | 👆️ (no change)                                 |
| `2.2.x` (`['>= 2.2.0', '< 4.0']`) | `gem "rubocop-lts", "~> 8.0"`  | `rubocop-ruby2_2` | 👆️ (no change)                                 |
| `2.3.x` (`['>= 2.3.0', '< 4.0']`) | `gem "rubocop-lts", "~> 10.0"` | `rubocop-ruby2_3` | 👆️ (no change)                                 |
| `2.4.x` (`['>= 2.4.0', '< 4.0']`) | `gem "rubocop-lts", "~> 12.0"` | `rubocop-ruby2_4` | 👆️ (no change)                                 |
| `2.5.x` (`['>= 2.5.0', '< 4.0']`) | `gem "rubocop-lts", "~> 14.0"` | `rubocop-ruby2_5` | 👆️ (no change)                                 |
| `2.6.x` (`['>= 2.6.0', '< 4.0']`) | `gem "rubocop-lts", "~> 16.0"` | `rubocop-ruby2_6` | 👆️ (no change)                                 |
| `2.7.x` (`['>= 2.7.0', '< 4.0']`) | `gem "rubocop-lts", "~> 18.0"` | `rubocop-ruby2_7` | 👆️ (no change)                                 |
| `3.0.x` (`['>= 3.0.0', '< 4.0']`) | `gem "rubocop-lts", "~> 20.0"` | `rubocop-ruby3_0` | 👆️ (no change)                                 |
| `3.1.x` (`['>= 3.1.0', '< 4.0']`) | `gem "rubocop-lts", "~> 22.0"` | `rubocop-ruby3_1` | 👆️ (no change)                                 |

#### All together now!

Upgrading a single step from odd to even will allow upgrading Ruby.

Upgrading a single step from even to odd will keep the same version of Ruby, and instead upgrade to the next RuboCop milestone.

Each major version will have a tracking branch named accordingly, [for development](https://github.com/rubocop-lts/rubocop-lts#git-branch-names).

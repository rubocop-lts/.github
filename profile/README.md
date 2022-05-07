## Hi there 👋

# 🙋‍♀️ How often has RuboCop broken your build?

This is both good (literally its job) _and_ bad (when it's for the wrong reasons).

It's supposed to break the build when it finds violations.
It should not break the build due to incompatibility with your environment.  RuboCop
doesn't follow SemVer, and occassionally it will unexpectedly break things.

# 🌈 Contribution guidelines

Each repository has a `CONTRIBUTING.md` document, as well as a section of the `README.md`
dedicated to development.  In addition each repository has a `CODE_OF_CONDUCT.md`, which
contributors must adhered to.

# 👩‍💻 Project Status

## Tools we use to solve Gorgon's Knot

| Your Ruby | Your Gemfile                   | Your Gemfile.lock |
|-----------|--------------------------------|-------------------|
| `1.9`     | `gem "rubocop-lts", "~> 1.0"`  | `rubocop-ruby1_9` |
| `2.0`     | `gem "rubocop-lts", "~> 2.0"`  | `rubocop-ruby2_0` |
| `2.1`     | `gem "rubocop-lts", "~> 3.0"`  | `rubocop-ruby2_1` |
| `2.2`     | `gem "rubocop-lts", "~> 4.0"`  | `rubocop-ruby2_2` |
| `2.3`     | `gem "rubocop-lts", "~> 5.0"`  | `rubocop-ruby2_3` |
| `2.4`     | `gem "rubocop-lts", "~> 6.0"`  | `rubocop-ruby2_4` |
| `2.5`     | `gem "rubocop-lts", "~> 7.0"`  | `rubocop-ruby2_5` |
| `2.6`     | `gem "rubocop-lts", "~> 8.0"`  | `rubocop-ruby2_6` |
| `2.7`     | `gem "rubocop-lts", "~> 9.0"`  | `rubocop-ruby2_7` |
| `3.0`     | `gem "rubocop-lts", "~> 10.0"` | `rubocop-ruby3_0` |
| `3.1`     | `gem "rubocop-lts", "~> 11.0"` | `rubocop-ruby3_1` |

🍿 Fun facts

Q: What does the team eat for breakfast each morning?

> Wild chicken eggs.  No, really.  Here in Indonesia they are called "telur kampung".  Also, jasmine tea.  

🧙 Now do the thing

`bundle add rubocop-lts -r false`

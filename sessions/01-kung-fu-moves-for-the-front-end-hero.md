# Kung Fu Moves for the Front-End Hero
1. Prevent regressions with Git hooks
   * Block commits when analysis errors are present
   * Do something simple; must execute quickly
1. Manage code complexity
   * jscomplexity.org evaluates cyclomatic complexity
   * Cyclomatic complexity is how many execution paths exist in the code
   * `cr -f plain file.js`
   * Consider maintenance/future readers when writing code
1. Monitor and track code coverage
   * Istanbul (NYC) for tracking coverage
   * Karma test runner has easy-to-enable coverage
   * Many online tools can consume the coverage report and track it over time
   * Coverage should be part of the ci/build system
   * Pull/merge requests should integrate with coverage and alarm/inform upon coverage decrease
1. Run quick smoke tests with evergreen browsers
   * Appveyor can easily run tests on windows
   * Chocolatey is a windows package manager
1. Test your downstream projects
   * Verify that changes don't break packages that depend on you

Parallelize when possible!

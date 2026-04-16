README Update

SilverDecisions - PeppVer (Rollback Display Fix)

This is a specialized fork of the SilverDecisions project. This version includes a critical "surgical" fix for the Rollback value display logic, specifically optimized for complex business analytics scenarios like the Magnolia Inn case study.

Website link: https://chat63791.github.io/SilverDecisionsPeppVer/

The Problem

In the original version of SilverDecisions, when viewing a decision tree, the "Rollback" labels on nodes often only displayed the isolated node payoff ($d$). For users performing Expected Monetary Value (EMV) analysis, this was misleading as it didn't show the cumulative value (the sum of the local node payoff and the rolled-back values from child branches).

 The Fix (PeppVer)
 
 I have patched the core logic in docs/app/gen/silver-decisions-core-1.2.1.min.js to ensure that the childrenPayoff display correctly reflects the total expected value.
 * Logic Change: The display value was updated from $d$ to $add(d, u)$.
 * Result: Decision and Chance nodes now display the Total Net EMV (Local Payoff + Cumulative Child Payoffs), matching manual rollback calculations used in business decision modeling.
 
 How to Run Locally
 
 If you want to run this fixed version on your own machine:
 1. Clone this repository.
 2. Navigate to the docs folder: cd docs
 3. Start a local server: python3 -m http.server 8080
 4. Open your browser to: http://localhost:8080/SilverDecisions.html

# SilverDecisions

Software for creating and analyzing decision trees.

Citation: 
B. Kamiński, M. Jakubczyk, P. Szufel: A framework for sensitivity analysis of decision trees, Central European Journal of Operations Research (2017).
[doi:10.1007/s10100-017-0479-6](https://link.springer.com/article/10.1007/s10100-017-0479-6)

If you are a SilverDecisions user please visit project [website](http://www.silverdecisions.pl) or [Wiki](https://github.com/SilverDecisions/SilverDecisions/wiki).

Basic technical information about SilverDecisions is provided in [Developer's Guide](https://github.com/SilverDecisions/SilverDecisions/wiki/Developer%27s-guide)

## User testing guide

* You can use `index.html` in `docs` directory to perform tests. Master contains current production version of SilverDecisions (and this version is served on the website), dev branch, if ahead of master, contains a development version.
* Submit atomic comments using GitHub issues
* Label usage guide:

| Issue label | Usage |
| --- | --- |
| `bug` | application does not work correctly |
| `needs doc` | aplication feature may be nonintuitive should be documented |
| `enchancement` | requests for new features |
| `question` | topics not directly related to development requests |

* Milestone usage guide:

| Milestone | Usage |
| --- | --- |
| `X.Y` | we plan to add the functionality in release `X.Y` |
| `hotfix` | we should fix it as soon as possible, possibly in minor release `X.Y.Z` |
| `unscheduled` | the functionality is planned but beyond last currently planned numbered relase |

[Bogumił Kamiński](https://github.com/bkamins) approves requests for enchancements and assigns them to development milestones.

# Smart Contract Reviewing

I prefer to call it "security review/smart contract review" rather than "smart contract auditing".

You might be wondering why this change of terms is required. Well, it’s because the term 'audit' might wrongly insinuate some kind of guarantee or even encompass legal implications. A security review, being free of these misconceptions, exudes the essence of what we are actually doing: looking for as many bugs as possible to ensure maximum code security.

## The Three Phases of a Security Review

```note
1. Initial Review
        a. Scoping
        b. Reconnaissance
        c. Vulnerability identification
        d. Reporting
2. Protocol fixes
        a. Fixes issues
        b. Retests and adds tests
3. Mitigation Review
        a. Reconnaissance
        b. Vulnerability identification
        C. Reporting
```

To give you a heads-up, there really isn't a "one-size-fits-all" approach to smart contract auditing. There are several unique strategies, each bringing a different set of pros and cons to the table.

>__!REMEMBER__
There isn’t a definitive, "correct" way of performing a security review.

### Importance of Security Reviews

A smart contract audit is a timeboxed, security based review of your smart contract system. An auditor's goal is to find as many vulnerabilities as possible and educate the protocol on ways to improve their codebase security and coding best-practices moving forward.

As code deployed to a blockchain is immutable, it’s crucial that it's error-free before deployment. The permissionless and adversarial nature of the blockchain means that protocols need to be ready to repel malicious users. Failure to do so can lead to hefty monetary losses, as evidenced by the nearly $4 billion stolen due to smart contract vulnerabilities last year.

The benefits of conducting a security review go beyond just minimizing vulnerabilities.

It also aids protocol developers in enhancing their understanding of the code itself, thereby accelerating feature implementation and increasing effectiveness. A security review can also familiarize your team with the latest trends and tooling in the space.

Often a single audit won't be enough, protocols are really entering into a security journey which may include:

* Formal Verification

* Competitive Audits

* Mitigation Reviews

* Bug Bounty Programs

With this understanding, let's familiarize ourselves with the process of a typical audit.

#### Reach Out for a Review

The review process begins when a protocol reaches out, be it before or after their code is complete. After they make contact, it's important to determine the cost of a review based on things like:

* Code Complexity/nSLOC

* Scope

* Duration

* Timeline

Lines of Code: Duration

* 100 : 2.5days

* 500 : 1 Week

* 1000 : 1-2 Weeks

* 2500 : 2-3 Weeks

* 5000 : 3-5 Weeks

* 5000+: 5+ weeks

Take this with a lot of salt though, as these timelines vary largely based on circumstance.

With the submission of a `commit hash` and `down payment` by the protocol and start date can be set!

>**!Note**: The `commit hash` is the unique ID of the codebase an auditor will be working with.

#### Audit Begins

Now that the admin work is done, auditors can roll up their sleeves and get to work. Using everything in their arsenal, they will strive to find as many vulnerabilities as possible in your code.

#### Initial Report

Once the review period is over, the auditors compile an initial report. This report includes all findings, categorized according to severity

* High

* Medium

* Low

* Information/Non-critical

* Gas Efficiencies

High, medium and low findings have their severity determined by the impact and likelihood of an exploit.

Informational/Non-Critical and Gas are findings focused on improving the efficiency of your code, code structure and best practices. These aren't vulnerabilities, but ways to improve your code.

#### Mitigation Phase
The protocol's team then has a fixed period to address the vulnerabilities found in the initial audit report. More often than not, they can simply implement the recommendations provided by the auditors.

#### Final Report
Upon completion of the mitigation phase, the audit team compiles a final audit report focusing exclusively on the fixes made to address the initial report's issues. Hopefully, this cements a strong relationship between the protocol and the audit team, fostering future collaborations to keep Web3 secure.

#### Ensuring a Successful Audit
For an audit to be as successful as possible, you should ensure that there's:

* Good documentation

* A solid test suite

* Clear and readable code

* Modern best practices are followed

* Clear communication channels

* An initial video walkthrough of the code

By considering auditors as an extension of your team, maintaining an open channel of communication, and providing them with the necessary documentation and context, you ensure the audit process is smoother and more accurate, providing auditors valuable context of the codebase.

#### Post Audit
Lastly, remember that a smart contract audit is an integral part of a security journey rather than an endpoint. Even after an audit, any subsequent code changes need to be reviewed as the new code is unaudited, regardless of the size of the change.

Remember: One audit might not be enough. Getting more eyes on your code is only going to increase the chances of catching vulnerabilities before it's too late

#### What an audit isn't
Going through a security review does not mean that your code is bug free. Security is a continuous process tha tis always evolving.

>**Remember:** "There is no silver bullet in smart contract auditing. But understanding the process, methods, and importance of regular security reviews can significantly enhance your protocol's robustness."

## Breakdown of the Audit Process

For a more detailed perspective, let’s consider the process as broken into three distinct phases:

**Initial Review**: The initial review of a protocol can also be broken down into 4 distinct phases.

* Scoping - This is getting a sense of the protocol. In this phase, auditors go through the code to scope it. This gives an idea of how much time might be required for the audit, which can then be used to establish pricing. Key tasks include identification of all the contract’s dependencies and a general overview of the code. At this stage, auditors don’t dig deep into anything yet.

* Reconnaissance - Here an auditor starts walking through the code, running tools, interacting with the protocol in an effort to break it.

* Vulnerability Identification - An auditor determines which vulnerabilities are present and how they're exploited as well as mitigation.

* Reporting - Compile a report detailing all of the identified vulnerabilities and recommendations to make the protocol more secure.

```note
"Your job is to do whatever it takes to make the protocol more secure."
```

**Protocol Fixes**: At this stage the protocol will take an auditor's report and work towards implementing suggested changes and mitigation. The length of time of this period can vary based on complexity of the issues, number of vulnerabilities identified and more.

**Mitigation Review**: Once a protocol has employed and tested all of the recommended fixes, a review is conducted with a focus on verifying that previously reported vulnerabilities have been resolved.

Your ultimate aim should be to make the protocol more secure. Therefore, ensure to take notes of all findings and steps and elaborate it in your report.

```note
Difference in Audit Types: Note that the aforementioned process details a private audit or a traditional security review. For competitive audits, you are typically optimized for time and identifying as many high vulnerabilities as possible.
```

## The Rekt Test

#### Audit Readiness
The concept that once you've had an audit done, you're ready to ship - is wrong. There are two tests that I tell everyone to look at prior to getting a security review one is the [nacentxyz simple-security-toolkit](https://github.com/nascentxyz/simple-security-toolkit) and the other is [The Rekt Test](https://blog.trailofbits.com/2023/08/14/can-you-pass-the-rekt-test/), by Trail of Bits

### The Rekt Test
The Rekt Test is highly important as it poses a set of questions to gauge your protocol's preparedness for an audit. This tool forces you to think about security measures from a more proactive angle. Should your protocols fail to answer these questions, the chances are that they're not audit-ready.

The questions touch on several aspects like documentation, security roles, security tools, and protective measures, among others. Here's a curated list:

1. Do you have all actors roles and privileges documented?

2. Do you keep documentation of external services contracts and oracles?

3. Do you have a written and tested incident response plan?

4. Do you document the best ways to attack your system?

5. Do you perform identity verification and background checks on all employees?

6. Do you have a team member with security defined in the role?

7. Do you require hardware security keys for production systems?

8. Does your key management system require multiple humans and physical steps?

9. Do you define key invariants for your system and test them on every commit?

10. Do you use the best automated tools to discover security issues in your code?

11. Do you undergo external audits and maintain a vulnerability disclosure or bug bounty program?

12. Have you considered and mitigated avenues for abusing users of your system?

As developers, you must be able to answer all these queries before you proceed with an audit. If you're dealing with a protocol that fails to answer these questions, it's best to tell them the protocol isn't ready to ship, or arguably audit, until they can.

### Nascent Audit Readiness Checklist

[This](https://github.com/nascentxyz/simple-security-toolkit) checklist is another effective method to assess if you're ready for an audit. Though it offers different perspectives, it's another tool that helps you determine if your protocols are prepared for audits.

## Tools for Security Reviews

#### Your First Line of Defense: Test Suites
Your classic test suite is your project's first line of defense. These are your frameworks like Foundry, Hardhat, Brownie, Apeworx - even Remix has tests.

#### Static Analysis: Debugging Without Execution
Static analysis represents the next level of defense. This method automatically checks for issues without executing your code, hence the debugging process remains static. `Slither`, `4nalyzer`, `Mythril`, and `Aderyn` are some prominent tools in the static analysis category.

#### Fuzz Testing: Randomness Meets Tests
Next we have Fuzz testing, which really comes in two flavours, `fuzz testing`(also known as fuzzing involves providing random data as inputs during testing) and `stateful fuzz testing`(fuzz testing, but the system remembers the state of the last fuzz test and continues with a new fuzz test)

#### Formal Verification: Mathematical Proofs
Formal verification is a broad term for deploying formal methods to affirm the correctness of hardware or software. Often, these methods involve converting the codebase into mathematical expressions and deploying mathematical proofs to authenticate that the code does or doesn't do something specific.

A popular formal verification approach is symbolic execution. This method converts your Solidity function into math or a set of boolean expressions. `Manticore`, `Certora`, `Z3` stand tall in this domain.

#### AI Tools: Not Quite There Yet

Lastly but importantly, AI tools offer another dimension to imagine code auditing functionalities. However, despite their potential, they have some distance to cover before they provide substantial value for securing a codebase. At present, using AI tools could serve as a sanity check or aid in looking for something quickly, but if a project suggests it has been audited by an AI tool like `ChatGPT`, it is best to be skeptical and question if the project takes security seriously.

There's a great GitHub repo by ZhangZhuoSJTU that illustrates examples of bugs that are detectable by machines and those that aren't. Check it out [here](https://github.com/ZhangZhuoSJTU/Web3Bugs).

### What If Your Security Audit Fails?
As the world moves towards a more digital infrastructure, the importance of security audits cannot be overstated. But who carries the blame when these audits fail? Should it always land at the feet of those responsible for conducting the audit?

#### Redefining the Role of Auditors
In the eyes of many, the fundamental purpose of a security audit is to identify and rectify the most critical vulnerabilities in a system. 

*Auditors should provide value, regardless of whether or not they spot critical issues.*

In other words, an auditor's value doesn't solely rest upon their ability to find vulnerabilities. Instead, their advice should strengthen the overall security protocol and offer pragmatic solutions for future scenarios.

Of course, it goes without saying that the fewer critical vulnerabilities that are overlooked, the better - the safer Ethereum will be. It's naive however to believe that an auditor is solely responsible for when things go wrong.

#### Who Owns the Blame?
The notion of finding a scapegoat when a system is exploited is a regressive one.

A whole chain of events leads to the successful exploitation of a vulnerability.

Attributing the failure of a system to an auditor's incompetency is simplistic and misguided. If a vulnerability was missed, it means it slipped past numerous stages of checks and balances, of which an audit is just one. When a flaw goes unnoticed for as long as four months, there are perhaps lapses in system monitoring and in many other security parameters.

#### The Auditor’s Role in the Wake of a Breach
So, what should an auditor do if a protocol they've reviewed ends up compromised? The answer is that a responsible security partner should not abandon their client in the midst of a crisis.

As an auditor, you may be able to help mitigate the damage, restrict the scope of the attack, and possibly identify the hackers. A quality auditor must be there, lending their expertise, during the inevitable chaos that ensues after a breach.

## Top Web3 Attacks

You should remeber or study the top web3 attack vectors, you can google it because these can change from time to timeS

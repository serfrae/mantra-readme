# CTO Business Plan
Thu 8 Feb 12:55:20 GMT 2024
@mantra @cto @plan

## Key Areas
What would be the plan for the next 3-6 months given the following:

1. What are some of the problems to be tackled with the pipeline of prospective products?
2. What is the proposed tech stack to be built upon?
3. Who are the people to be hired and how would the team be formulated?
4. What are the initial challenges that are to be faced?
5. Who are the key stakeholders to be engaged and collaborated with?

Where relevant, more detail can be found in their respective sections contained within this document.
Detailed sections only provide an overview where needed and are not meant to be exhaustive or provide a granular level of detail.

### Summary
#### Overview
Assuming a start before the end of February and a two (2) to four (4) week lead time to get up to speed, a general timeline for the next 3-6 months is outlined as follows:
1. The primary focus needs to be securing the right talent, and thus from a CTO's perspective, ensuring the interview and subsequent onboarding process
is refined for efficiency. It is expected that the aforementioned will take place over a two (2) month or less period depending on the efficacy of
our recruiters and screening (wrt to potential candidates) processes.
2. Once the right talent has been secured, our impetus revolves around subsequent training and ensuring our chosen team can execute the requirements 
of the DEX, Orderbook, and Chain.
3. The obvious challanges are centered around the implementation of a high performance on-chain orderbook, as highlighted below, this is a non-trivial task
and will require a significant amount of technical colloboration and experience.

#### Timeline
Our timeline, for a mainnet launch with the expected primitives are as follows:
If a visual version of the following is more suitable one can be provided:
March -> April: Onboarding, and procurement of the Phase I development team. In conjunction, items ___ delineatd in the section "mainnet launch: are applicable:
2, 4, 5, 6, 7, 8, 11.
Furthermore, as Phase II tesnet is already slated for an April (latest) lauch there is little to do in terms of further development.
April (Launch of Testnet Phase II) -> Mid May: Necessary steps to begin development of the required DEX features.
Mid May -> Mid June: Standard processes required to build to SoW for the orderbook and start development. 
Mid June -> August: Battle-test the orderbook and DEX: all of the checklist as defined in the mainnet section are relevant.
September: Mainnet.

### Product Pipeline:
#### Testnet Phase II
As I expect that this has been built out to a sufficient degree as to enable our counter-parties to test the currently developed and battle-tested modules.
It would therefore be reasonable to assume that the a significant portion of the DEX in regards to what is relevant for 
the mainnet launch is true for our Testnet Phase II, as such relevant details are found in the section for the mainnet lauch.

#### Mainnet
1. Thorough code audits and security checks.
2. Implement a rigorous QA process.
3. Ensure scalability and performance testing.
4. Validator reliability and security.
5. Continuous integration and continuous deployment (CI/CD).
6. Network monitoring and incident response.
7. Continuous improvement and updates.
8. Community engagement and support.
9. Redundancy and failover mechanisms.
10. Implement geographically distributed nodes and redundant infrastructure to ensure network resilience even in case of partial outages.
11. Employ redundant storage solutions to prevent data loss and maintain transaction integrity.
12. Disaster recovery plan.
13. Network governance and community consensus.

#### DEX
Many of the items required for mainnet are also applicable to the DEX since the DEX is built directly into the application layer of the chain.
As such all of the above that are relevant for mainnet are relevant to the DEX, however the following from the aforementioned are unecessary:
4, 9, 10.

As previosly mentioned the DEX's core code is already built into the application layer however, there are key functionalities as required by Mantra that the current
iteration may not provide. Assuming that the DEX's code is, in its current form, identical to that of the Crescent protocol from which the 
Mantra chain is forked, there are features that Mantra require to be suitably built. 
Thus, one of the first things to be tackled is the implementation of said required features as defined by the product team.
Assuming that this has not been done already we will have to go through the standard processes of:
1. Requirements gathering and analysis
  - Identify features, functionalities and the scope of the work needed to be done.
  - I.e. Requirements and objectives.
2. Planning and design
  - Roadmap the timeline for the implementation of said features.
  - Resource allocation.
  - Define the deliverables.
3. Development and testing
Once the above items are complete, deployment and implementation of the DEX will follow the same lifecycle as that outlined above for mainnet.

#### CLOB
To implement a central limit orderbook off-chain, is trivial, however an on-chain implentation is relatively difficult / non-trivial. There exist avenues we can explore to reduce development time.
I.e. dYdX - they have implemented their own orderbook that is completely on chain; because finality appears to be instant on dYdX it is likely that they have implemented 
a different consensus algorthim than what is currently implemented by CometBFT i.e. Tendermint.

The most feasible implementation of an instant finality consensus algorithm is HotStuff, however, dYdX have kept their implementation of the aforementioned consensus algorithm, proprietary.
Such an undertaking is non-trivial and requires a development team with sufficient experience and understanding of this architecture to modify and implement.

It is therefore necessary to build phase I of the development team in earnest unless we plan to outsource such an undertaking. However, outsourcing such an endeavour
exposes Mantra to a litany of risks chief among them being the maintenace of the codebase and technical debt.

#### Primitives
Currently out of scope.

### Tech Stack:
1. CometBFT - This replaces Tendermint as the underlying BFT consensus engine. Provides faster consensus mechanisms such as HotStuff.
2. Cosmos SDK - The core framework for building application logic and modules.
3. CosmWasm - A powerful Wasm-based smart contracting platform that can be plugged into the Cosmos-SDK easily.
4. IAVL Tree - The default immutable ledger implementation. 
5. ABCI - The interface for connecting CometBFT with the application logic built using SDK.
6. Protobuf - For serializing and encoding transactions and messages.
7. gRPC - For API communication between CometBFT and application.
8. Go - The main programming language used to build custom modules and transactions in Cosmos SDK.
9. Rust - The main programming lanugage used to build smart contracts utilising CosmWasm on the Cosmos SDK.
11. JavaScript/TypeScript - For building frontend applications and wallets.
12. Vue/Svelte - For constructing UI components and pages.
13. Vite - For frontend developer tooling.
14. PostgreSQL/Bigtable - For storing off-chain or supplemental data.
15. Docker - For containerizing and deploying network nodes and services.
16. Google Cloud Storage - For storing historical chain data and backups.
17. Telemetry - Prometheus, Grafana etc. for monitoring, metrics and alerting.

### Development Team Expansion:
1. Phase I - estimated timeframe of two (2) months
 - One (1) Senior Developer (Head of Engineering)
 - Two (2) Fullstack Developers
 - One (1) Security Engineer / Reliabilty Engineer
 - One (1) DevOps Engineer
Total headcount: Five (5).

2. Phase II - estimated time frame of up to (2) months
 - Two (2) Senior Developers
 - Two (2) Fullstack Developers
Total Headcount: Nine (9).

AGILE teams are cross-functional, therefore the need for a project manager is minismised and can be
subsumed within the role of Product Owner, barring which, such a team should be self-organising and
able to render the role of a PM relatively redundant, precluding the need for such a position.

### Key Stakeholders
1. The CEO - John
2. Head of Mantra Chain - Jayant
3. Head of Product - Charu
4. The Community / Users
5. Validators / Node Operators
6. Liquidity Providers and Custodians

## Product Pipeline
The current Mantra ecosystem is comprised of three (3) main products, these being:
1. The Mantra chain.
2. The decentralised exchange (DEX) for tokenised real word assets (RWA).
3. The central limit orderbook (CLOB) for RWAs.
4. (Nice to have(s)) Other relevant DeFi primitives i.e. lending which I currently define as out-of-scope.

### Mantra Chain
In order to ensure a successful launch of the blockchain, the following key steps must be executed:

#### Pre-Launch Preparations:
1. Thorough code audits and security checks:
  - Conduct internal and external security audits by reputable firms to identify and address vulnerabilities before going live.
  - Employ static code analysis, penetration testing, and smart contract audits to assess potential exploitable code and logic flaws.
  - Utilise formal methods and tools to mathematically prove the correctness and security of critical components, especially smart contracts.
  - Engage ethical hackers through bug bounty programs to identify and disclose vulnerabilities before launch.
  - Utilise threat modelling to proactively identify and assess potential attack vectors and implement corresponding mitigation strategies.

2. Implement a rigorous QA process:
  - Implement a well-defined QA process involving unit, integration, and system testing for all components (core platform, smart contracts, APIs, etc.).
  - Ensure that test-driven development (TDD) has been utilised to ensure code meets pre-defined functionalities and behaviours.
  - Employ automated testing frameworks for continuous regression testing and rapid feedback loops.
  - Fuzz test by injecting random data into the system to uncover unforeseen edge cases and potential vulnerabilities.
  - Chaos test by deliberately introducing disruptions (network partitions, resource constraints) to assess system resilience and recovery protocols.
  - Performance profiling by identifying performance bottlenecks and optimise critical code paths for efficiency.
  - Test upgrades and hard forks on the testnet first. Ensure the network continues to function properly after upgrades.

3. Ensure scalability and performance testing:
  - Stress test the network under varying loads to identify performance bottlenecks and assess its ability to handle anticipated transaction volumes.
  - Implement load balancing to enhance scalability and prevent overload scenarios.
  - Monitor key metrics like latency, throughput, and resource utilisation during testing to measure performance.
  - Compare the network's performance with established platforms under similar loads as a benchmark.
  - Utilise blockchain simulation frameworks to model complex scenarios and assess network behaviour under realistic conditions.
  - Utilise load injectors to continuously bombard the network with simulated traffic to identify breaking points and optimise for peak loads.
  - Push the limits of the network until it fails to establish max capacity.
  - Test network recovery under heavy load. Verify nodes resync properly after downtime.
  - Analyze and profile system performance - throughput, latency, memory, CPU, disk, etc. Optimize any bottlenecks

4. Validator reliability and security:
  - Establish clear validator selection criteria based on technical expertise, hardware specifications, and commitment to network uptime.
  - Implement monitoring and alerting systems to detect and address validator downtime or malicious behaviour.
  - Create a validator forum/channel for validators to get support and communicate with each other

5. Continuous integration and continuous deployment (CI/CD):
  - Automate code building, testing, and deployment processes to ensure rapid bug fixes and feature updates.
  - Implement rollbacks and canary deployments to minimise impact in case of unforeseen issues.
  - Infrastructure as code (IaC): Manage and provision infrastructure in an automated and repeatable manner for seamless deployments.
  - Containerization: Package code and dependencies into standardised units for consistent and portable deployments across environments.
  - Version control: Maintain a well-defined version control system to track changes, facilitate rollbacks, and ensure code traceability.

#### Launch and Post-Launch:
1. Network monitoring and incident response:
  - Proactively monitor network health with dedicated dashboards and real-time alerts.
  - Establish an incident response plan to address unexpected issues, bugs, and potential security breaches.
  - Have a clear communication strategy to inform the community about any network issues and resolutions.
  - Real-time dashboards: Gain real-time insights into network health, resource utilisation, and transaction rates.
  - Alerting and notification systems: Proactively be notified of anomalies, potential issues, and security threats.
  - Post-mortem analysis: Thoroughly analyse incidents to identify root causes and prevent future occurrences.

2. Continuous improvement and updates:
  - Analyse post-launch data to identify areas for optimization and performance improvement.
  - Release regular updates with bug fixes, security patches, and new features based on community feedback and roadmap.
  - Agile development methodologies: Adopt flexible and iterative development approaches to respond to changing requirements and community feedback.
  - DevOps collaboration: Foster close collaboration between development, operations, and security teams for efficient problem-solving and updates.
  - Community code contributions: Encourage and facilitate community involvement in code development and testing for wider participation and ownership.

3. Community engagement and support:
  - Offer comprehensive documentation, tutorials, and educational resources for users and developers.
  - Establish user support channels to address questions and concerns effectively.
  - Community forums and channels: Provide dedicated spaces for open dialogue, technical discussions, and community collaboration.

#### Checks and Balances:
1. Redundancy and failover mechanisms:
  - Implement geographically distributed nodes and redundant infrastructure to ensure network resilience even in case of partial outages.
  - Employ redundant storage solutions to prevent data loss and maintain transaction integrity.

2. Disaster recovery plan:
  - Develop a comprehensive disaster recovery plan to restore the network quickly and minimise downtime in case of catastrophic events.
  - Regularly test and update the disaster recovery plan to ensure its effectiveness.

3. Network governance and community consensus:
  - Establish clear decision-making processes and governance mechanisms for resolving disputes and implementing upgrades.
  - Regular security audits and penetration testing: Continuously assess the network's security posture and address vulnerabilities proactively.
  - Have a mainnet dry-run 1-2 weeks before launch and invite external auditors/engineers to test the network.
  - Develop a pre-launch checklist covering testing, documentation, support systems, infrastructure, etc.
  - Have a rollback plan in case any major issues emerge on the mainnet.
  - Recruit external network monitors to track health metrics post-launch. Establish an on-call rotation schedule to respond to incidents.
  - Continuously monitor network stability and performance in the first few weeks. Quickly address any issues that come up.
  - Conduct a post-mortem review of the launch process to capture learnings for the future.

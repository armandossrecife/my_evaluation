# my_evaluation

# Evaluating the ATDCodeAnalyzer method

To evaluate the [ATDCodeAnalyzer](https://github.com/Technical-Debt-Large-Scale/atdcodeanalyzer), we executed the following steps:

1. **Development of an Inspection Labeling Process**: We created a process to label inspections, facilitating the identification of issues with potential architectural impacts.

2. **Analysis of Four Open-Source Repositories**: Employing the ATDCodeAnalyzer, we extracted critical classes from each repository and examined the behavior of critical classes and issues with architectural impact.

# Analysing Issues with Architectural Impact

Analysis of [commits and issues](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/analysis_commits_issues.jpg) from Git Repositories using Critical Classes from [ATDCodeAnalyzer](https://github.com/Technical-Debt-Large-Scale/atdcodeanalyzer/blob/main/docs/diagrams/AnalysisCassandraRepositoryFlow.png).

We have been analysed four Java Software project Git Repositories: [Apache Cassandra](https://github.com/apache/cassandra), [Apache ActiveMQ](https://github.com/apache/activemq), [Apache Kafka](https://github.com/apache/kafka) and [Apache Hadoop](https://github.com/apache/hadoop). We evaluated 678 issues from Cassandra (226), ActiveMQ (132), Kafka (179) and Hadoop (141) using an inspection aided by the LLM model to classify them as either Yes or No based on their architectural impact.

We selected a representative dataset of Git repositories, encompassing significant source code repositories such as Apache Cassandra, Apache Kafka, Apache Hadoop and Apache ActiveMQ. These repositories exhibit complex software architectures, boasting many attributes, including more than 10000 commits, over 100 collaborators, over 1000 Java files, over 100000 lines of code, and at least ten-year lifetime. Consequently, these repositories are characterized by substantial commit histories, many contributors, intricate codebases, and widespread adoption within the software industry. Each repository's numerical and metric attributes will be comprehensively detailed. We applied the [ATDCodeAnalyzer](https://github.com/Technical-Debt-Large-Scale/atdcodeanalyzer) method to the repositories to identify critical files impacted by Architectural Technical Debt.

We examine if these issues indicate architectural problems within the software. These problems encompass: software's structure, organizational issues, quality software, issues that impact evolvability and maintainability. For example: changes to core components,performance improvements, scalability snhancements, concurrency and parallelism, resource management, data model changes, distributed system aspects, consistency and availability, extensibility and plugin frameworks, security and compliance, system modularity, data integrity and durability, etc.

Related to "architectural impact issues" found by **issues in commits with critical classes** in the selected software repositories: 

RQ0) What is the proportion of issues classified as impacting architectural design, as observed in each analyzed software repository?


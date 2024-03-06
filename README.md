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

**Understanding the Research Questions:**

RQ0: This question focuses on the prevalence of architectural impact issues in each repository. You can calculate the percentage of issues classified as "Yes" for architectural impact for each repository to answer this question.

## Apache Cassandra analysis

Draft of Cassandra's commit and issue analysis method

![My analysis of commits and issues from Cassanddra](https://raw.githubusercontent.com/armandossrecife/my_validation3/main/imagens/my_method_analysis_commits_issues.jpg)

1. Filtering (A) - Cassandra Project:
This step involves selecting and filtering data related to the Apache Cassandra project from the GitHub repository.

3. Filtering (A) - Commits with Critical Classes:
After filtering the Cassandra project data, you further narrow down the focus by identifying commits that involve critical classes. Critical classes may be those that are related to architectural or high-impact changes.

4. Filtering (B) - Cassandra Project:
In this step, you do a similar filtering process but on the Jira Issue Tracker, specifically looking for issues related to the Cassandra project.

5. Filtering (B) - Issues with Commits with Critical Classes:
This step involves identifying Jira issues that are associated with commits containing critical classes. It's a way to link code changes with corresponding issues.

6. Random Sample Selection from 4 that results in 226 issues:
Here, you randomly select a subset of the filtered issues. The reason  is for further analysis.
Based on a normal continuous random variable from [ScyPY](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.norm.html)
Based on the parameters: confidence_level = 0.95, margin_of_error = 0.05, population_proportion = 0.8 and population_size = len(issues_with_commits_with_critical_classes)
sample_size = calculate_sample_size(confidence_level, margin_of_error, population_proportion, population_size)
norm.ppf(): normal continuous random variable

7. Manual classification of issues to check architectural impact:
You manually review and classify the selected 226 issues to assess their architectural impact. This could involve identifying whether the issue relates to architectural changes, refactoring, or other factors. The manual inspection process is detailed in this [link](https://docs.google.com/document/d/1umbEJMVsdxTzBVOr8VDRCscpwOK9-ePVJ-o862L5j08/edit?usp=sharing)

9. Semi-automatic classification aided by ChatGPT with Prompt Engineering:
In this step, you use ChatGPT to assist in the classification process. You might provide prompts to ChatGPT to help automate or semi-automate some of the classification tasks. More details in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/inspection_process.md

10. Degree of Agreement Calculation comparing 6 and 7:
This step involves calculating the degree of agreement between the manual classification and the semi-automatic classification performed with the help of ChatGPT. You need to quantify how closely the two methods align.

11. Degree Agreement using Cohen's Kappa:
Cohen's Kappa is a statistical measure used to assess the agreement between two raters (in this case, the manual and ChatGPT-assisted classifications). It takes into account the possibility of agreement occurring by chance.

The calculated Cohen's Kappa score was found to be 0.721, indicating a substantial level of agreement between manual inspection and ChatGPT inspection.

In our evaluation of the model used for inspecting issues, we obtained the following key performance metrics: Precision: 0.962, Recall: 0.833, Accuracy: 0.867 and F1-Score: 0.893.

More details about evaluation of precision of inspection process is available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/evaluate_inspection_model.ipynb

This semi-automatic inspection process (aided by ChatGPT) can help to inspect other issues from other apache projects. 

More details and scripts are available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_cassandra.ipynb

## Apache ActiveMQ analaysis

ActiveMQ analysis

![My analysis of commits and issues from ActiveMQ](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_method_analysis_commits_issues_activemq.jpg)

More details and scripts available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_activemq.ipynb

## Apache Kafka analysis

Kafka analysis

![My analysis of commits and issues from Kafka](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_method_analysis_commits_issues_kafka.jpg)

More details and scripts available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_kafka.ipynb

## Apache Hadoop analysis

Hadoop analysis

![My analysis of commits and issues from Hadoop](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/my_method_analysis_commits_issues_hadoop.jpg)

More details and scripts available in https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/my_analysis_hadoop.ipynb

# Results

The comparison of **issues in commits with critical classes** among Cassandra, ActiveMQ, Kafka and Hadoop

## RQ0 - What is the proportion of issues classified as impacting architectural design, as observed in each analyzed software repository?

![% of architectural impact by Repository](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/architectural_impact_by_repo.png)

![Issues with architectural impact by Repository overtime](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/issues_with_ai_overtime.png)

![Commits with Critical Classes overtime](https://github.com/Technical-Debt-Large-Scale/my_validation/blob/main/imagens/commits_with_critical_classes_overtime.png)

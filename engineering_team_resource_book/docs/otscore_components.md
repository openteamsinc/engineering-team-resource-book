# Components of the OpenTeams Score

## 1. Security Risks
### Known as Common Vulnerabilities and Exposures (CVEs)
### Data Sources:
- Scan the project with [one of the open-source security (CVE) tools](https://awesomeopensource.com/projects/cve)

- Check to see if there is a bug report on the project on [Bugzilla](https://bugzilla.redhat.com/)


- [WhiteSource Vulnerability DataBase](https://www.whitesourcesoftware.com/vulnerability-database/projects) (this is a paid service)


- Also, check out [WhiteSource Free Developer Tools](https://www.whitesourcesoftware.com/free-developer-tools/)



- ...

## 2. IP risk
### Will someone claim my derivative work, is all the code really licensed for me to use.
- There are over 200 types of licenses that can be applied to open-source software, including Apache, GPL, and MIT. Many of these licenses are incompatible with each other, meaning that certain components cannot be used together since you have to comply with all terms when using open-source software. The more components you use, the more difficult it becomes to track and compare all of the license stipulations. Companies want to ensure that they are remaining compliant with open source licenses and protecting themselves from business or reputational risk. The most common IP risks that arise from the use of open source software today, include Copyright infringement, Patent infringement, Reputational risk, Exposure of IP secrets, The impact on the partner/customer relationship, the concept of viral or copyleft licenses. Being aware that no license means default copyright laws apply.
Low risk: Permissive licenses:
- Permissive licenses generally do not have real limiting conditions. Rather, they usually require that you keep the copyright notice in place when you distribute your own software. This basically means that you can use and change the open source software as needed as long as you keep the copyright notices intact. Some top open source licenses in this category are the Apache and MIT licenses. We rate permissive licenses as LOW risk licenses.
Medium risk: Semi-permissive licenses:
- Semi-permissive licenses usually require that if you modify the open source code, you make these modifications available under the terms of the given license. Some of these licenses explicitly define what a modification is. For instance, they might consider copying unmodified open source code into proprietary code to be a modification. To comply with the license obligations, the developer would have to release the source code (original, modified, and newly added). The most popular open source licenses in this category include the Mozilla and the Eclipse Public Licenses. We rate semi-permissive licenses as MEDIUM risk licenses.
High risk: Restrictive licenses:
- Some top open source licenses, such as GPL 3.0 and AGPL, are quite restrictive. Depending on how you integrate the open source software with your proprietary software, you may face significant risk. In the worst-case scenario, you may be required to release your proprietary software under the same license—royalty-free. We rate restrictive licenses as HIGH risk licenses. [source: Synopsys](https://www.synopsys.com/blogs/software-security/top-open-source-licenses/)

**Copyleft and permissive licenses: what’s the difference?**

Both copyleft and permissive licenses allow developers to copy, modify, and redistribute code (derivative or otherwise) freely. The most important difference between the two, however, lies in how each approaches copyright privileges.
While permissive licenses allow developers to include their own copyright statements, copyleft licenses provide no such privilege. Instead, copyleft license rules require all derivative works to be subject to the original license. This means that developers cannot make patent or copyright claims on the original software.
According to research by White Source, the most popular permissive licenses are MIT and Apache 2.0, with BSD in a distant third place. The GNU GPLv3 is the most popular copyleft license but is steadily losing market share compared to permissive licenses. [Source: Comparison of Pupolar Open Source Licenses](https://www.kiuwan.com/comparison-popular-open-source-licenses/)

**Recent Trends in Open Source Software Licenses**

In 2020, the use of copyleft licenses continued to decrease while permissive licenses increased in their popularity.
'''{image} ../images/whiteSourse_liscense_trend_chart_2020.png
'''
[Image credit: WhiteSource](https://www.whitesourcesoftware.com/resources/blog/open-source-licenses-trends-and-predictions/)

### Data Sources:
- [FOSSA](https://fossa.com/product/open-source-license-compliance) License Compliance  (paid service)
- A categorization of existing licenses from the most permissive to the least permissive

## 3. Governance 
### Is the project well-governed?
### Data Sources:
- Github/Gitlab project repo - Does the project have a governance document (bylaws, IP policy, membership policies, board composition, etc.) OR
- An expression of responsibilities, privileges of contributors exists in the repo
- Formalized leadership roles definition in the repo (README or elsewhere)
Meritocracy
- Check the diversity among company affiliations of the project committers and their contributions over the last 12 months. For example, nine committers out of a total of 11 all coming from the same organization, and having been in place for several years is generally problematic.
- Is the leadership “earned”?
- Are the key decisions about the project public?
- Is the governance (leadership team) broad?
- Does each contributor have an equal say in the acceptance of a piece of code?
- Broad governance also means that there are functioning input flows from different teams within a project, such as user and advisory groups. Even if the governance has a BDFL structure, the project can still have broad governance by giving the contributors a chance to have an impact on key decisions
- Do user groups of the project have a way to provide input into the technical direction of the project
- Are the leaders governing the input from users & contributors
- Metrics for good governance: assessment of the governance quality of an open-source project cannot always be abstracted in numbers. Instead, find a list of characteristics – both quantitative and qualitative – that are indicators as to whether a project is more or less well-governed. “a sign of good governance is that there are clear procedures and norms to transfer governance between individuals. This must include an expression of the responsibilities and privileges of individuals contributing to a project or teams of people collaborating on specific areas of subject matter expertise (marketing, integration testing, docs, etc.) within a project.”
*Patterns in issue resolutions. (Analysis of commentary)
- Differences of opinion on the technical direction are an innate part of open-source projects. Check for evidence of successful issue resolution as a proof-point for good governance.

## 4. Popularity
### Usage, number of users, dependent projects, domain area
### Data Sources:
- Github/Gitlab data (forks count, star count, number of projects dependent on this project, download stats)
- Web visibility (have social media accounts, forums, frequent discussions on or about the project on forums, StackOverflow data related to questions on the project, etc.)
- The project repo has main components (contributing guide, code of conduct, readme, documentation, etc.)

## 5. Community Health
### Contributors around the project
### Data Sources:
- Overview of community, which should require consideration of an open-source component’s history, such as the density of known issues, version release frequency, and latency between issue identification and patch. It is important to know how robust the community involved in a project is and anticipate what sort of support it might or might not provide.
- Github/Gitlab data (libraries.io SourceRank score?): Is the repository of the project is well maintained, does the project have a documentation page, how good is the documentation?
- Quality risk of the project: what qualifies a project to be of high quality, there is no standard to assess open source code quality”, popularity does not always guarantee quality.
- Diversity of contributors -- how difficult is it for someone to become a new contributor.  Are there systems in place to attract diverse contributors?  Are there new issues identified?  Are there mentors who can bring in new contributors?

## 6. Version risk
### How supported is the version you are using
### Data Sources:
- For projects that use versioning, what is the most recent version, and what is the oldest version the project team still provides support for?

## Immediate Action Items:
- Ask for feedback from open source software maintainers, contributors starting with people at OpenTeams and Quansight about the components listed above & make adjustments as needed
- Review the methods [CHAOSS](https://chaoss.community/) and their metrics used to calculate their score and refactor the applicable parts to our score
- Implement the pipeline/algorithms to gather and calculate a score. This will entail multiple ways of gathering, processing, normalizing, and aggregating the data, such as scraping, using the data sources available, implementing ML/NLP models to process data on the project, and providing predictions, algorithms to calculate the score for each component’s data based on the sources listed above (and potentially more).

## Deliverables
- A scoring algorithm to calculate the score for each component and each open source project we are interested in based on the data we collect.
- A database that stores the score components and final score of each project
- A tool that can take a conda environment file or a docker manifest and score the environment based on all the dependencies.
- Make the score available on the project pages
- When QHub Inc, creates a conda-store environment page -- have the environment score listed.
- Talk to Anaconda about having environments hosted on anaconda.org have the score.
- Create an API so that anyone can list the score for the project and/or environment from our algorithm.
- A feedback mechanism on the project pages for community contributors to understand how the score is calculated and update the data leading to the score. Guide them to how they can do it by identifying other projects, resources, or experts who could help them and pointing them to those resources.
- Make a command-line tool so that a developer can run the tool over a conda environment, docker container, or other deployment-specific artifacts to get an overall score for the environment.



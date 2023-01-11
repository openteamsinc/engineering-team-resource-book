# Engineering 

## The Issue of Technical Debt 


***Software development is rarely sustainable. The average organization wastes 23- 42% of their development time due to technical debt.***

There are competing ideas about what constitutes technical debt. The prevailing definition states that in software development, technical debt is the implied cost of additional rework caused by choosing an easy solution now instead of using a better approach that would take longer. Along those lines, and within the context of our team, technical debt is how we define what “done” means. We will refine our understanding of “done” as we improve our practices, however, to begin with, it means:
Any task that you confirm to be “done” is a task that has been tested preferably through automated testing and continuous integration throughout the development cycle. “Done” also means, if it is a piece of software, it is documented and follows the coding guidelines in this guide, as well as other areas of best practices in software development that this guide might be lacking in its current iteration. 


## Coding Style Guides and Rules 


It is much easier to understand a codebase when all the code in it is in a consistent style. At the OpenTeams Engineering Team, we are currently in the process of establishing a set of specific software development rules and best practices governing all of our codebases. 

This guide should be adopted by the OpenTeams Engineering Team members and are not suggestions and may not be disregarded except as approved on a need-to-use basis. As a natural consequence of adopting some of the empirically substantiated standards of programming, our team’s goal is to **improve efficiency, collaboration,** and **enhance our individual and collective software engineering skills.**


## Development Specific Requirements 


As a developer member of the OpenTeams Engineering Team, you are expected to follow the requirements and meet the expectations in this document in its current form and any updated version in the future, as well as other unwritten requests that your team leads, project manager, or the members of the OpenTeams leadership might have. 


## Gitlab Issues 


- Each team member should have an issue that has a clear description of the task they are currently working on, and acceptance criteria, **using the appropriate issue template on Gitlab for your task**, as well as any of the other details needed at any time that they are at work. 
- Each issue should have an estimate attached to it when it is created and an actual time spent tag when it is closed. 
- Before an issue can be closed, the amount of time spent on the issue needs to be stated. No issue should be closed without the time spent. This allows everyone collectively to get better at scoping tasks in the future and allows us to have a history of the amount of hours projects and/or tasks have taken. 
- When you create an issue for a given task, please use label(s) that specifies the project and the nature of task using the scoped labels, as well as normal labels, in as much detail as possible.  Please let your team lead know if you need other scopes under a given project label in addition to the existing ones as you create your tasks in issues. There are currently a few general scopes, such as development, documentation, bug, enhancement, etc. for each project. We will create more of these as needed to make our issues more descriptive. 
- Issues that result in code, documentation, or any other type of data or file that will be added to the repository need to be reviewed by a reviewer and any suggestions the reviewer provides should be resolved before they can be closed. The person who will review the code should be assigned as a “reviewer” on Gitlab merge requests. The reviewer is often the tech lead or team members who are working on the same project. 
- If you are assigned as a reviewer, you should review the code as soon as possible. If you will not be able to review within a reasonable amount of time (i.e. **< 24h**), please find another reviewer on the team as soon as possible. If you can’t find another reviewer, let the tech lead know. 
- If your reviewer has not reviewed your MR **in 24h**, first let them know, ideally soon after the first 24h. If after you have contacted the reviewer and you have waited a reasonable amount of time, you still have not received the code review, let the tech lead know. 
- If you are provided a code review by your reviewer, and the suggestions are minor, depending on your other current tasks and their priorities, you should aim to respond to your reviewer as soon as possible. The goal is to close MRs in an improved state as soon as possible after the code reviews are responded and suggested and needed modifications are made. This minimizes multiple branch conflicts and interference with continuous development. 
- If the task defined in an issue diverges from its original state when it was created, evolves into a different task, or considerably changes its scope, these and any subsequent actions, as a result, should be noted in the issue description. 
- When you complete working on an issue, please put it in the Review tab on the dashboard (Gitlab) unless requested otherwise to receive code reviews and/or feedback from other team members and/or team lead.
- If an issue did not result in the expected outcome, there should always be a note regarding what you tried, what was expected, and what did not work in the issue comments before the issue is closed. If requested, the findings should be logged in other formats/places, as well.
- **Slack vs Gitlab Issue commenting:**
    - When a discussion needs to be had on a given issue with the other members of the team, such as when you have a problem, a bug, need clarification, need help etc. related to a given issue on Gitlab and you need someone else’s attention to it, describe the problem in the comment section of the Gitlab issue by tagging the Gitlab username of the specific team member if you know who can help with the issue you are having. Then, copy and paste the URL to the issue in the Slack channel (for now, our main communication channel is #engineering-team channel) and tag the Slack name of the person who needs to attend to the issue/discussion. 
- Use the **#engineering-team channel** for all team/task related conversations even if it is a task that is seemingly between you and only one other team member unless, of course, it is not appropriate to do so (i.e. the conversation has private, or sensitive information that only the recipient should read). This will help other team members step in if your primary and intended audience is not available at the time, or others might also have useful insight, solutions, and/or answers to a problem you might be experiencing. In other words, *avoid DMs as much as possible and when it makes sense to do so* to allow more transparency within the team, and take advantage of potential opportunities to get help that you might, otherwise, not be able to.


## Code Quality


The code you write and push to the team repository could be considered a demonstration of your *current* software engineering skills. We write code for others to be able to read, understand, use, extend and maintain if needed without the need for the author of the code to explain it. It is true that the most opinionated topics usually come up when you talk about achieving readability, maintenance, and extensibility. However, your code should demonstrate your best effort for such qualities to the best of your knowledge and the feedback you receive. Our goal as a team is to be coherent in our choices about writing software. It goes without saying that your code should be readable, follow the general best practices of computer science/programming, and apply the widely accepted style guidelines of the programming language you are using if they exist. 


## Coding Style 


A common vocabulary of coding allows engineers to concentrate on what their code needs to do rather than how they are doing it. This also allows us to optimize for the reader of the code. We would rather the code be tedious to type than difficult to read. 

Currently, the primary language of development for data analysis and AI/ML specific development in the team is Python. For many of the other domains of development we implement (backend, web development, deployment etc.), we use the appropriate programming language. You can use any language that fulfills the task at hand, as long as it is compatible with the rest of the codebase, or is the only choice you have to complete a task. Since programming languages have different strengths, different features, and different priorities, for the sake of practicality, we independently tailor our guidelines to specific programming languages, starting with Python and JavaScript. 

The code you push to the engineering team project repositories needs to: 
*PS: Some of the items below can be automated with precommit hooks and CI/CD pipelines in the future.*

1. Have exception handling anywhere it is needed, particularly when your code interacts with an external resource (API queries, DB access, reading files, etc.) 
2. Have logging when appropriate and useful, which is often. 
3. Have explicit evidence of intended behavior in your code 
4. We will start following style guides specific to the programming languages we use for our development. This approach primarily aims to make all of our development practices easier as it will significantly reduce the amount of time we might need to spend to figure out the details of the script we are working on, reviewing, trying to understand, or debug. 
    - For Python: we will follow the [Google Python Style Guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md#38-comments-and-docstrings) for comments and docstrings. Google Style Guide shares some aspects of [PEP 257 - Docstring Conventions](https://www.python.org/dev/peps/pep-0257/) but also has some more intuitive conventions that aim to make the code more readable. Code reviews will take into account if a given script follows the guidelines and will not be merged to adhere to the style so that we can attain a uniformly written style for the entire codebase.
    - For JavaScript: we will follow [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html). If you are not familiar with these style guides, please take the time to learn them. 
    - If the primary language you need to use in your development is not listed here, please let your team leaders know and we will discover and add the most appropriate style for that language into this guide. 
5. Run a formatter on your code before you push it to the team repositories, preferably Black, which formats Python code without compromise. 
    - When to check your code’s quality? 
        1. Frequently 
        2. As you write it 
        3. When it is checked into a repository 
        4. When you are running your tests 
        5. Git pre-commit hooks can be set up locally to run the linter before committing.
        6. Have been cleaned up - no commented out code, etc. 
        7. If using Jupyter Notebooks, have outputs cleared from any warning or error messages. The only output you should have on your notebook that is pushed to git should be the actual output of the notebook that you would like others to see. Additionally, since Jupyter notebooks do not have strict execution order, make sure to “Restart and Run All" before you push your notebook to ensure that each cell is in the order that they need to be to run the entire notebook and attain the intended execution order without error. 
        8. Have no hard coding unless it is unavoidable/needed 
        9. Have no inline magic numbers unless it is unavoidable/needed 
        10. Have no typos (can easily be solved by a linter) 
        11. In sections using the English language (docstrings, comments etc.), have correct grammar, succinct use of language etc. Google has a great resource on this: [Link](https://developers.google.com/style) 
        12. Not violate any privacy rules about the data it uses 
        13. Have tests implemented 


## Issues and Merge Requests 


Both issues and merge requests now have their own pre-defined templates that we will use when we are creating issues or submitting merge requests. The templates have been adopted from other software engineering teams’ best practices survey results that have reported proven increase in communication and productivity in daily engineering tasks. 

By writing well defined issues, we guarantee that we understand the task, we are able to communicate its requirements and its acceptance criteria, and we demonstrate that we have done the preliminary thinking about how to solve the given problem. Similarly, by adopting a merge request template with relevant information about a given merge, we are able to demonstrate that we have done our due diligence as much as possible when requesting our code to be merged to the rest of the codebase and what specific issue/problem/task the merge request we are creating solves, all of which are extremely useful information to other members of the team. Moreover, such practices aim to improve our personal engineering practices. 


## Documentation 


Documentation is highly valued in OpenTeams’ Engineering Team. Some of the many benefits of well-written documentation include being one of the most efficient ways to unblock team members, onboard new members to the team, and prevent misunderstandings regarding tasks and functionalities of tools/source code. Write the Docs has a wide range of resources about how to write documentation. It is also a great community to be a part of. Please take some time to learn the basics (ideally more) of how to write documentation by consulting to this (and other) resources if you are tasked with writing documentation. 
- All code, projects and procedures to build or deploy a system that the team works on needs to be documented in an appropriate and/or in a specifically requested format. For code-level documentation, for example, your code needs to have docstrings and inline comments, when the intent is not always obvious, in methods. 
- Larger documentation needs should be addressed through a format that is appropriate or requested. We are working on standardizing our documentation practices in the coming months. 


## Code Reviews 


In our team, we want to use code reviews as an opportunity for a culture of collaboration and learning. While reviewing someone else’s code, use thoughtful language and select your words constructively. 

Code review is a process in which code is reviewed by someone other than the author, often before the introduction of that code into a codebase. The code review enables us to: 
- Review, comment and improve each other’s code. 
- Approval workflow of the code review process enables reviewing and approving changes. - Have asynchronous review and give and receive feedback on our code. 
- Learn from each others’ development practices, mistakes, and strengths. 
Some comments request explicit resolution. Some are merely informational. Some of the primary goals of code review is to improve the readability and maintainability of the code base and identify potential bugs. The review process supports such software engineering practices that make development better 
for the entire team. However, having a well-defined code review process is only one part of the code review story. 


### Reviewers 

- Explain why the developer should make the change you are recommending. - There are often multiple solutions to a programming problem and your approach or preferences might not be the same as the author of the code you are reviewing. Thus, you should articulate your choices and explain your reasoning, and any clear advantages or disadvantages to the changes you recommend (performance gain, readability, compatibility, probable issues with the current version of the code, etc.). 

#### Resources on Code Reviews 
- [Humanizing Peer Reviews](https://www.processimpact.com/articles/humanizing_reviews.pdf) 
- [How Code Reviews Build a Company Culture](https://www.fullstory.com/blog/what-we-learned-from-google-code-reviews-arent-just-for-catching-bugs/) 
- [Code Review Guidelines](https://www.codeproject.com/Articles/524235/Codeplusreviewplusguidelines) 
- [Why Review Code?](https://smartbear.com/learn/code-review/why-review-code/)
- [Understanding the Code Review Process](https://smartbear.com/learn/code-review/guide-to-code-review-process/) 
- [Gitlab has a number of useful tools to make development and code reviews easier and more efficient](https://about.gitlab.com/stages-devops-lifecycle/code-review/)
- [Why code reviews matter (and actually save time!)](https://www.atlassian.com/agile/software-development/code-reviews)

#### Code Review Checklist 
- To make it easier for the reviewer, we will develop a checklist and utilize some of Gitlab’s features for code review. This information is upcoming. 


## Testing and Writing Tests 


Testing your code needs to be an indispensable part of your development process. Including tests in your MR, together with your code, makes it a lot easier for your colleagues to integrate your code into other parts of a project or identify potential problems that you might not have noticed. Making sure that your code is functional is your responsibility. 

“Writing tests for X” should **not** be a separate issue, as it is expected, by default, to be part of the task detailed in an issue and listed as an item of the checklist of the acceptance criteria for any task that requires some type of testing (i.e. pretty much any scripting that does something). Please see Appendix, Issue Template Sample Listing Tests as Part of the Task for an example of how to integrate testing as part of a given task described in an issue. 




If you have any questions or concerns about this guide, feel free to contact your team leads. 

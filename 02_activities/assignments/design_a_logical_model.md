# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

![ERD Q1](https://github.com/user-attachments/assets/0f710cc4-5229-400d-8515-1c0ac2e6e477)


At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

![ERD Q2](https://github.com/user-attachments/assets/c9315d20-92d7-4ccf-aaeb-714b09a87c34)


## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

![ERD Q3](https://github.com/user-attachments/assets/4213714b-2772-424c-b6c0-115b1a3cf260)

Bonus: Are there privacy implications to this, why or why not?
```
Type 1 SCD:
Description: This method updates the customer address by replacing the old address with the new one. It does not keep any past address information.
Behavior: When a customer changes their address, the previous address is overwritten, and only the latest address is saved.

Privacy Implication:
Loss of Historical Data:
Reason: When a customer updates their address, the previous address is permanently deleted. This can impact audits, customer verification, and compliance with legal requirements that may necessitate maintaining historical data.
Trust Issues:
Reason: Customers may not be aware that their past addresses are not retained. This lack of transparency can lead to distrust in the business, as customers may feel their data is not being managed responsibly.

Type 2 SCD:
Description: This method keeps a history of addresses by creating a new record each time a customer updates their address.
Behavior: When a customer updates their address, a new record is created, while the old record remains with effective dates. This way, all previous addresses can be tracked.

Privacy Implication:
Increased Data Volume:
Reason: Storing all historical addresses leads to a larger database, which can increase the risk of data exposure in a breach. More data means more potential points of vulnerability.
Compliance Challenges:
Reason: Keeping historical data longer than necessary can lead to non-compliance with data protection regulations, which often require businesses to limit data retention and justify its necessity.

```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
The main difference between AdventureWorks and my ERD are:

AdventureWorks applies a high degree of normalization, splitting data into many smaller, interconnected tables to avoid redundancy and ensure efficiency. In comparison, my ERD maintains a more straightforward structure, which works well for smaller systems but may lead to duplication of data as complexity increases.

AdventureWorks organizes its tables into distinct schemas (e.g., Sales, Human Resources), separating data by functional domain. My ERD consolidates all entities into a single schema, which is efficient for a smaller project but may become harder to manage as time goes on.

While my ERD's simpler design is effective for its current purpose, applying a more normalized structure and separating functional areas into schemas would enhance scalability, making it easier to manage larger datasets and future growth.
```

# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `September 28, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-4-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.

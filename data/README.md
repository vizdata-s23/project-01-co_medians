# data

The datasets we are using are from TidyTuesday (https://github.com/rfordatascience/tidytuesday/tree/master/data/2022/2022-06-07) and come from the website Data For Progress. This data contains 6 separate datasets: pride_aggregates, fortune_aggregates, static_list, pride_sponsors, corp_by_politician, and contribution_data_all_states.

After looking into the datasets further, we realized that there was overlap of information in static_list, fortune_aggregates, and pride_aggregates. Static_list captured the most complete information from fortune_aggregates and static_list combined, so we decided to use that dataset. We decided not to focus on specific pride events nor on politicians, so we didn't use the pride_sponsors dataset. We did use the contribution_data_all_states dataset, as that provided date information (for use in time-series plots), contribution amount, and if the contribution was towards pride or anti-LGBTQ campaigns. We also used the corp_by_politician dataset because it had information on the office/title held by the politicians who received donations.

## Static_list

Each row corresponds to a company; a few of the variables we are using from this dataset for our analysis include `Pride?`, `HRC Business Pledge`, and `Amount Contributed Across States`.

| Variable                               | Description                                                                        |
|------------------------|------------------------------------------------|
| `Company`                              | The name of the Fortune 500 company.                                               |
| `Pride?`                               | Did the company donate and/or sponsor Pride events?                                |
| `HRC Business Pledge`                  | Did the company sign the HRC Business pledge?                                      |
| `Amount Contributed Across States`     | The total amount of money contributed to anti-LBGTQ politicians in the U.S in USD. |
| `#of Politicians Contributed to`       | The number of anti-LBGTQ politicians the company contributed to.                   |
| `# of States Where Contributions Made` | The number of states where the company made anti-LBGTQ contributions .             |

## Contribution_data_all_states

Each row denotes a single donation along with the company who made it; some of the variables we are using to answer our research questions from this dataset are `Pride?`, `Date` (which we extracted the column `Year` from), and `Amount`.

|                            |                                                                   |
|----------------------|--------------------------------------------------|
| **Variable**               | **Description**                                                   |
| `Company`                  | The name of the Fortune 500 company.                              |
| `Pride and Sponser Match?` | Does the company company sponsor Pride events or Fortune or both? |
| `Pride?`                   | Did the company donate and/or sponsor Pride events?               |
| `HRC Business Pledge`      | Did the company sign the HRC Business pledge?                     |
| `Donor Name`               | The name the donation was made under.                             |
| `Politician`               | The name of the politician the company contributed to.            |
| `State`                    | The state the politician is running in.                           |
| `Amount`                   | The total amount of money contributed to the politician in USD.   |
| `Date`                     | The date of the contribution.                                     |
| `Donor Type`               | Was the donation PAC or Group/Business/Corporation?               |

## Corp_by_politician

| Variable      | Description                                                                                     |
|---------------|-------------------------------------------------------------------------------------------------|
| Politician    | The first and last name of the politician                                                       |
| SUM of Amount | The total amount of contributions in USD the politician received from business in the data set  |
| Title         | The office or official title the politician holds, for example "Governor" or "Senator"          |
| State         | The state in which the politician holds office                                                  |

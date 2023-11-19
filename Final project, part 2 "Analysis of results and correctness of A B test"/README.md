# Final project, part 2: Analysis of results and correctness of A/B test
Description and objectives of the project
Our task is to evaluate the results of the A/B test. We have a dataset with user actions, a technical task and several auxiliary datasets at our disposal.
We need to evaluate the correctness of the test and analyze its results.
The most important stages of verification:
- make sure that there are no intersections with a competing test and there are no users participating in two test groups at the same time;
- check the uniformity of the distribution of users in test groups and the correctness of their formation;
- determine the users participating in the test;

To determine which users participate in the test, we need to:
- check who is participating in the test according to the task;
- next, from the user data, leave only those who came from the target region;
- next, it is necessary to leave out of the received users those who did not get into both groups of the test and those who did not get into group B of the competing test;
- finally, the remaining users need to check whether they have committed events or not. It is necessary to leave only those users who committed the events;
## Skills and tools
- python
- pandas
- matplotlib
- seaborn
- numpy
- scipy
## Conclusions
It is impossible to say that the test was conducted correctly. This was influenced by the following factors:
- Group A initially had many more users than Group B
- it turned out that there are many more users in group B who did not commit any events
- since we decided to delete users who were in group B of a competing test and users who did not commit the event, as a result, we had about 3,000 users left, while 6,277 users were required for the correct conduct of the test.

As a result, we got a situation where there are fewer users than necessary and the test groups are disproportionate. As a result, in group A, users committed much more events, which affected the conversion.
Also, the test coincided with the Christmas&New Year Promo event, respectively, it is impossible to say that users were not subjected to any external influence, and in my opinion this is another reason why it is impossible to say that the test was conducted correctly.
## Recommendations for the test:
1. Conduct a test when there are no marketing activities in the target region.
2. Change the mechanism for distributing users into groups so that groups A and B are more proportionate.
3. Improve the mechanism of attracting users so that it is the target audience that will make events and, accordingly, the number of users without events will decrease.
4. Revise the value of the indicator of the relative difference between the test groups from 5% to 10%, since then a smaller sample will be required for the correct conduct of the test.

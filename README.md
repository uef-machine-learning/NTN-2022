# Nordic Twitter Network (NTN-2022)

## Overview
The NTN-2022 dataset is a network dataset focused on Twitter users within the Nordic countries between November 2016 and November 2022.
<br />
<br />
Contact: [masoud.fatemi@uef.fi](masoud.fatemi@uef.fi)

## Usage
This dataset is intended for academic research and analysis focused on the empirical structure of social relations within the Nordic Twittersphere. Users are encouraged to cite our paper in any resulting work.

## Cite
M. Fatemi, S. Sieranoja, M. Laitinen, and P. Fränti, "Cluster Analysis of Nordic Social Media Users Based on Connection", *Submitted to Nordicom Review*, 2024.

## Dataset Creation Process
The dataset was developed in 4 steps: **user extraction**, **labelling**, **filtering**, and **tweet collection** across the entire network. Here is a brief overview of the steps involved:

![image](https://github.com/Masoud-Fatemi/NTN_2022/assets/25830298/021b1a7c-a1c2-4edf-a1e8-19898e5582e0)
<br />
  1. **User Extraction:** Initially, all Twitter users with tweets in the [Nordic Tweet Stream (NTS)](https://erepo.uef.fi/handle/123456789/6697) from November 2016 to November 2022 were extracted.
  2. **User Labeling:** Users were then labelled based on the country from which they tweeted, focusing exclusively on the five Nordic countries. Users tweeting from more than one country (travellers) were excluded to maintain geographical consistency.
  3. **User Filtering:** This step involves filtering out users based on several criteria: <br />
    - Exclusion of users with uncertain locations or whose self-reported location did not match their tweet locations. <br />
    - Remove verified accounts to focus the dataset on regular users. <br />
    - Filtering based on the network size, excluding users with more than 500 contacts, the top 1% most active, and the bottom 1% least active accounts. <br />
  4. **Tweet Collection:** For the final user list, we collected up to 3,200 of the latest messages per user, excluding retweets.
<br />
Once these steps finished, directed links were established based on interactional relationships, and only the largest connected component was retained.

## Dataset Composition
The NTN-2022 dataset comprises 3,273 nodes and 13,483 directed edges, representing user interactions. The dataset includes detailed country labels for each node, indicating the user's location among the five Nordic countries (FI=Finland, SE=Sweden, NO=Norway, DK=Denmark, IS=Iceland).
<br />
<br />
**NOTE**: For privacy reasons, the collected tweets will not be made public, and user IDs have been anonymized.

## Files Included
- **network.txt:** Contains all nodes and directed edges from each node to others. Line format:  
  - First number: id of node (in range 0..(N-1))
  - Second number: K = Number of neighbors
  - Next K values: the ids of the K neighbors
  - Next K values: the weights  to the K neighbors (its an unweighted graph, all wieghts equal to 1)
 
Lines end with '\n' (including last line).

Example row: 
```
1 5 399 442 238 0 444 1.0 1.0 1.0 1.0 1.0 
```
Second node id = 1, K = 5, neighbors = [399 442 238 0 444], weights = [1.0 1.0 1.0 1.0 1.0]  


- **labels.txt:** Includes node IDs and their corresponding country labels.

## Statistical Summary
**Nodes:** 3,273 <br />
**Links:** 13,483 <br />


|         | Finland| Sweden | Norway | Denmark | Iceland |
| ------- | ------ | ------ | ------ | ------- | ------- |
|  Nodes  | 1,275  | 1,001  |  362   |   516   |   119   |


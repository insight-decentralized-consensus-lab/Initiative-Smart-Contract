![else: https://i.imgur.com/wrtkd0N.png](https://i.imgur.com/VkIZT0v.png)

Create a dev crowdfunding smart contract or DApp using GitHub as the progress oracle. Included pseudocode below for a good outcome. 

### Smart contract parameters:
-  REPOSITORY: [URL]
-  REVIEWER_LIST: [List of GitHub accounts]
-  N_MINIMUM_APPROVE: [Integer]
-  PAYOUT_AMOUNTS: [Array of numbers, payout for each milestone]
-  PAYMENT ADDRESS: [string]
-  DESCRIPTION: [Paragraph describing project & milestones]

### Smart contract pseudocode:
Let `PR_X` be a GitHub pull request with a subject line that starts with “[Milestone X]”

```
If PR_X at REPOSITORY is approved 
by at least N_MINIMUM_APPROVE GitHub users from REVIEWER_LIST
then dispense PAYMENT_AMOUNTS(X) to PAYMENT_ADDRESS
```

The smart contract would also have cases to handle underfunding (depends on whether for consulting project or hire), overfunding (pay out extra to Insight upon merge into main codebase), non-chosen projects (contract dissolves and refunds donors if repository not created within 18 months), and non-satisfactory projects (extra funding goes back to supporters OR some donation address, e.g. general BTC development fund).

### Example:

REPOSITORY: 
https://www.github.com/insight-decentralized-consensus-lab/Monero_Subliner_Ring_Signatures

REVIEWER_LIST: 
@SarangNoether, @suraeNoether, @moneromooo, @samsunggalaxyplayer, @IsthmusCrypto

N_MINIMUM_APPROVE: 
3

PAYOUT_AMOUNTS: 
15, 15, 40

PAYMENT ADDRESS: 45GtemxMdbdaSvjCqWA4aJY3L4QUwEpUs2Rka5Rpu8yz9Sg5wpjbHs4SUviz4

DESCRIPTION: 
Implement sublinear ring signatures that...  Milestone 1: MVP // Milestone 2: PR into Monero repository // Milestone 3: Merged into Monero’s codebase… Reviewers are Devs and NRL...

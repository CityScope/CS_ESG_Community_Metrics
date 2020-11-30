# CS_ESG_Community_Metrics
A tool for calculating community-level ESG metrics

## 15-minute communities
All metrics are calculated over the area inside a 15-minute accessible isochrone from the place of interest. For example, the metrics for block group X will be based on the community which is accessible within 15 minutes from the centroid of block group X. The mode of accessibility will generally be walking but for some metrics (eg. hospital access), driving accessibility will be used.

The 15-minute communities for each block-group are computed in a pre-processing stage of the analysis. For walking accessibility, a network distance of 1200m is used as the limit (based on 4.8km/hr walkng speed). For each block-group, the following steps are carried out:
- Identify the block-groups which are within 1200m straight line distance
- Of this subset, get the walking distance on the network to each block_group using the OSRM routing API. 
The results are saved as a json file where the keys are block-group IDs and the values are lists of accessible block-groups.
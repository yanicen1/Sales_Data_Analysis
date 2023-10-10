## Sales Data Analysis

<b>Technical Task</b>

1. Calculate metrics using the following measures:
- Revenue
- Profit
- Profitability
- Active Client Base
- Average Order Value
- Logistics Costs

2. Create the following graphs:
- Metrics in a dynamic view
- Metrics by customer segment
- Metrics by product category, subcategory, and product name with drill-down capabilities
- Metrics with geographical distribution on a map

3. Perform an ABC analysis of items and present the results in a table.
  
4. Display a table listing managers who have generated negative profits and the number of orders with negative profits.


## Solution
The solution is available in the form of PowerBI dashboards within the [Project_1](https://github.com/yanicen1/Sales_Data_Analysis/blob/main/Project_(ABC_without_categories).pbix) file, where the ABC analysis of items is conducted without category segmentation, and Project_2, where the ABC analysis of items is conducted with category segmentation. You can view the dashboard layouts in this [PDF file](https://github.com/yanicen1/Sales_Data_Analysis/blob/main/Project_(ABC_without_categories).pdf). The data set is presented [here](https://github.com/yanicen1/Sales_Data_Analysis/blob/main/Dataset.xlsx).

Additionally, some insights were uncovered:
1. There is a bidirectional relationship between the Sales and SPR_Customers tables, which introduces some uncertainty. For instance, customer Alex Avila belongs to two buyer segments (Home Office and Corporate) and has made three purchases. Consequently, it's unclear to which segment each purchase should be attributed. The bidirectional link in the model assigns all three purchases to both the first and second segments. Consequently, the amounts for such cases double, leading to an increase in metrics when aggregated by segments. For example, the actual revenue (approximately 1.1 million) is lower than the segment-calculated revenue (1.25 million), resulting in a 12% disparity. This issue could likely be resolved by adding the order ID to the "Customers" table to establish a more specific linkage between the tables using this column.
2. When calculating orders with negative profits while switching from Managers to Order_ID, the total profit and the number of orders decrease (278 and 277, respectively). This discrepancy occurs because, in some cases, one order can have two different managers assigned to it. Additionally, within a single order, there can be multiple products with both positive and negative profits. Consequently, when aggregating profits for orders and managers, the result can vary, with some showing negative profit and others positive. Notably, negative profits are captured by the filter, but positive profits are not.

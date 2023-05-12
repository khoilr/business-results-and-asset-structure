# Business results and asset structure

## Business results

To crawl data from **CafeF**, we can use the `requests` library to send a GET request to the website and retrieve the HTML content. We can then use the `BeautifulSoup` library to parse the HTML content and extract the financial data from the table.

The table contains the financial data for each quarter, with the first row being the header and the second row being the revenue data. We need to find the column labeled as ‘Lợi nhuận sau thuế’ or ‘Lợi nhuận ròng’ to extract the profit data.

After extracting the data, we need to clean it by removing the ‘Quý’ prefix from the quarter, and multiplying the revenue and profit by 1000 to convert the unit from **Thousand Dong** to **Dong**.

Finally, we can use the `plotly` library to visualize the data in a bar chart. We can create a `Figure` object and add traces for the revenue and profit data, and then customize the layout and display the chart.

![Business results](./Business%20results.png)

## Asset structure

The task is to crawl data from the website CafeF using the `request` and `BeautifulSoup` libraries. The resulting HTML should be parsed to locate the tables with ids `tblGridData` and `tableContent`. The former contains the header of the data, which includes the quarters, while the latter contains the actual data.

When iterating through the rows of the ﻿tableContent table, if the title of the row matches any of the following:

- i - tài sản ngắn hạn
- ii - tài sản dài hạn
- i. tài sản

Then the row should be skipped, as it represents a summary of the data.

If the title of the row matches either of the following:

- tổng tài sản
- tổng cộng tài sản

Then the loop should be broken, as this indicates the end of the current data.

After crawling the data, we need to clean it by removing the word ‘Quý’ from the quarter and any commas from the numerical values. Then, we can use the `plotly` library to create a bar chart to visualize the data.

To create the chart, we can first create a `Figure` object and add traces for the revenue and profit data. We can then customize the layout of the chart, such as the title, axis labels, and legend. Finally, we can display the chart.

![Asset structure](./Asset%20structure.png)

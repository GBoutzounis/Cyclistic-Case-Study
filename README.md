# Cyclistic Case Study: Analyzing User Behavior

**Author:** Ioannis Boutzounis  
**Last Updated:** 19/9/2026

Cyclistic is a successful bike-share company based in Chicago with a fleet of over 5,800 bicycles and 600 docking stations. Cyclistic's finance analysts have concluded that annual members are significantly more profitable than casual riders. This project analyzes historical bike trip data to identify trends in user behavior, aiming to provide data-driven recommendations to help the marketing team design a targeted strategy to convert casual riders into annual members.

## Data Source & Reliability
*   **Origin:** Historical, public bike trip data covering Q1 2019 and Q1 2020.
*   **Provider:** Data is made available by Motivate International Inc.
*   **Privacy:** Strict data-privacy protocols were followed, ensuring that all personally identifiable information (PII) regarding the riders has been excluded.

## Tools & Methodology
Data aggregation, cleaning, and preparation were conducted entirely in Excel, while Tableau was utilized to create one of the final data visualization.

## Data Engineering
*   Created a `ride_length` variable by subtracting the start time from the end time, formatted as HH:MM:SS.
*   Created a `day_of_week` variable using the WEEKDAY formula to map start dates to numerical days (1=Sunday, 7=Saturday).
*   Renamed 2019 Q1 columns (e.g., changing `trip_id` to `ride_id` and `from_station_name` to `start_station_name`) to align with the 2020 Q1 schema.
*   Standardized user classifications in the 2019 Q1 data by updating "Subscriber" to "member" and "Customer" to "casual".

## Data Cleaning
*   Merged the 2019 Q1 and 2020 Q1 datasets into a single workbook (`merge_spreadsheet`).
*   Scanned for and confirmed zero duplicate entries in the `ride_id` column.
*   Cleaned station names by replacing asterisk (*) artifacts with a space (861,853 changes).
*   Removed internal company testing rows linked to the "HQ QR" station.
*   Eliminated outliers by excluding anomalous trips lasting less than 1 minute or longer than 24 hours.

## Key Insights

*(Note: To view the full Tableau visualizations supporting these insights, please refer to the **`Cyclistic_Case_Study.pdf`** presentation included in this repository.)*

*   **Weekly Ride Volume:** Annual members display high, consistent usage Monday through Friday, indicating they primarily use Cyclistic for daily commuting. In contrast, casual rider volume remains low during the workweek but nearly doubles on Saturdays and Sundays, indicating leisure use.
*   **Average Ride Length:** Casual riders take trips nearly 3 times longer than annual members, averaging 35+ minutes per ride (recreational, leisure use) compared to ~12 minutes for members (quick, point-to-point commutes). This pattern remains consistent across all seven days of the week.
*   **Top 20 Start Stations:** The highest-traffic stations in the network are heavily dominated by members, who drive almost all the volume at these locations. Casual riders represent a very small fraction of starts at these specific high-traffic commuter spots.

## Recommendations

*   **Create a "Weekend-Only" Membership:** Offer a tailored annual plan specifically for riders who use bikes on Saturdays and Sundays.
*   **Advertise Cost Savings:** Launch a campaign showing casual riders how quickly an annual membership pays for itself on trips lasting longer than 30 minutes.
*   **Target Leisure Locations:** Focus physical and digital advertising near parks and recreational areas during peak weekend hours, rather than at commuter-heavy stations.

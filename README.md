# Hotel-booking-demand

## Project overview

The project analyses 119,390 booking records from a city hotel and a resort hotel from 2015 to 2017, with details like hotel type, booking behavior, customer profile, and distribution channel. The aim is to understand reservation patterns across the two hotels and to identify the factors behind the city hotel's notably higher cancellation rate. The dataset is loaded into Deepnote for analysis with Python, and the main results are presented in a Power BI dashboard. 

## Business questions
- How do reservation volumes, pricing and cancellations differ between the two hotels across the year?
- Do cancelled bookings have longer lead times than completed bookings?
- Why does the city hotel have a higher cancellation rate than the resort hotel?

## Data source
- Source: Hotel Booking Demand dataset (Antonio, de Almeida and Nunes, 2019, Data in Brief), available on Kaggle. A copy is stored in ['data/archive.zip'](data/archive.zip)
- Size: 119,390 rows × 32 columns (79,330 city hotel bookings; 40,060 resort hotel bookings).
- Key fields: hotel type, cancellation status, lead time, arrival date, length of stay, guest numbers, deposit type, customer type, market segment and average daily rate (ADR, in euros).

## Tools
| Tool | Purpose |
|---|---|
| Python (pandas, NumPy) | Data cleaning and manipulation |
| Matplotlib, Seaborn | Charts and correlation heatmap |
| SciPy | Welch's t-test and chi-square tests |
| Power BI | Interactive dashboard |
| Deepnote | Notebook environment |

## Method

### 1. Data cleaning
- Missing values were filled rather than dropped: children, agent, and company with 0, and country with "unknown".
- 31,994 rows were identical to another row. These rows were retained, because the dataset has no unique booking ID and identical rows may represent genuine separate bookings; removing them could understate demand.

### 2. Descriptive analysis 

Booking and cancellation counts by hotel, the lead-time distribution, and monthly bookings, ADR and cancellations for each hotel.

### 3. Exploratory analysis

A correlation heatmap of cancellation, lead time, ADR, length of stay, guest numbers and booking history.

### 4. Diagnostic analysis

Welch's independent t-test comparing the lead times of cancelled and completed bookings.
Chi-square tests of independence between cancellation and three categorical factors: deposit type, customer type and market segment. Each was followed by a comparison of how those categories are distributed across the two hotels.

## Dashboard Preview 
<img width="635" height="359" alt="Hotel booking dashboard" src="https://github.com/user-attachments/assets/7f1053ef-723f-4256-b97f-d18cb8e6258f" />

## Key Insights
- The city hotel had a significantly larger number of monthly reservations than the resort hotel over the year. Both hotels' reservations reached their peak in August.
- The city hotel's pricing was stable throughout the year. The resort hotel had clear seasonality with a June-August peak.
- The city hotel had a much higher cancellation rate than the resort hotel. This is because of the city hotel's lead time, deposit type, and distribution channels.
- Cancelled bookings had longer lead times than completed bookings.

## Recommendation 
- The hotels could leverage the peak season in the summer months to maximise their revenue.
- To improve the cancellation rate, the city hotel should adopt strategies to encourage shorter booking lead times, try more effective cancellation policies, and diversify its booking profile. The city hotel could also develop a predictive analytics system to identify high risk reservations. 

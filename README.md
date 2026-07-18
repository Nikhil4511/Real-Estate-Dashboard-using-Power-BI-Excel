# 🏠 Real Estate Sales Dashboard — Power BI Project

An interactive **Power BI Dashboard** for a global real estate business, tracking property sales, revenue, expenses, profit, and agent performance across **30 countries** from **2025 to 2027** — built with a custom purple-themed UI, 3D icons, dynamic map, and image carousel.

---

## 📸 Dashboard Preview

### 2025 View
<img width="604" height="334" alt="Screenshot 2026-07-18 183815" src="https://github.com/user-attachments/assets/0e5a2717-b08b-4fbd-85bb-571989bb3b09" />

### 2026 View
<img width="1183" height="663" alt="Dashboard realstate image" src="https://github.com/user-attachments/assets/2a1994b1-f3c0-4572-8c27-eda4fd24502f" />

### 2027 View
<img width="599" height="334" alt="Screenshot 2026-07-18 183850" src="https://github.com/user-attachments/assets/583477e4-721b-4631-8a6a-ac75d0bd3d03" />


---

## 📁 Repository Structure

```
real-estate-powerbi-dashboard/
│
├── 📊 Dashboard_Real_State.pbix           # Final Power BI dashboard
│
├── 🔢 Step-by-Step Build Files/
│   ├── 1__Importing_data_and_slicers.pbix
│   ├── 2__MAP_Visual.pbix
│   ├── 3__Bar_chart_and_max_min_formula.pbix
│   ├── 4__Top_N_Card_and_Metric.pbix
│   └── 5__Line_Chart_and_carousel_chart.pbix
│
├── 📂 Data Sources/
│   ├── Property_details.csv               # 84 properties — main dataset
│   ├── Customer_Details.xlsx              # 10 real estate agents
│   ├── Calendar.xlsx                      # Date table for time intelligence
│   └── Json_MAP_File.json                 # Custom map for geo-visual
│
├── 🎨 Assets/
│   ├── Background.png                     # Custom purple dashboard background
│   ├── Revenue.png                        # 3D KPI icon
│   ├── Expense.png                        # 3D KPI icon
│   ├── Profit.png                         # 3D KPI icon
│   └── Property.png                       # 3D KPI icon
│
└── README.md
```

---

## 📋 Dataset Overview

### 1. `Property_details.csv` — Main Dataset

| Property | Details |
|---|---|
| **Total Properties** | 84 |
| **Sold** | 69 properties |
| **Vacant** | 15 properties |
| **Countries Covered** | 30 countries |
| **Year Range** | 2025 – 2027 |
| **BHK Types** | 1 BHK to 5 BHK |
| **Price Range** | ~6.2L – ~14.9L (USD) |

#### Columns

| Column | Description |
|---|---|
| `Unique Property ID` | Unique ID for each property |
| `Name of Country` | Country where property is located |
| `Type of BHK` | Bedroom count (1–5 BHK) |
| `Size of home` | Size in square feet |
| `Price` | Selling price (USD) |
| `Expense` | Expense incurred for the property |
| `Status` | Sold / Vacant |
| `Sale Date` | Date of sale (DD-Mon-YY format) |
| `Client ID` | Foreign key linking to Customer Details |
| `Image` | URL of the property image (Pexels) |

#### Countries Covered (30 countries)
Argentina, Australia, Brazil, Canada, Chile, China, Egypt, France, Germany, India, Indonesia, Italy, Japan, Malaysia, Mexico, New Zealand, Nigeria, Norway, Philippines, Russia, Saudi Arabia, South Africa, South Korea, Spain, Sweden, Thailand, Turkey, United Kingdom, United States, Vietnam

---

### 2. `Customer_Details.xlsx` — Agents / Clients

| Column | Description |
|---|---|
| `ClientID` | Unique agent/client ID |
| `Name` | Agent full name |
| `Img` | Agent profile photo URL |

**10 Agents:** James Smith, Emma Johnson, Liam Brown, Olivia Jones, Noah Williams, Ava Taylor, William Davis, Sophia Wilson, Benjamin Moore, Isabella Anderson

---

### 3. `Calendar.xlsx` — Date Table
Custom date dimension table used for **time intelligence** in DAX — enables year, quarter, and month-level filtering.

---

### 4. `Json_MAP_File.json` — Custom Map
Custom GeoJSON map file used in Power BI's **Shape Map visual** to display country-level revenue distribution with a purple color gradient.

---

## 📊 Dashboard Visuals & Features

| Visual | Description |
|---|---|
| 🗺️ **Custom Shape Map** | World map highlighting countries by revenue using JSON file |
| 📋 **Country Revenue Table** | Scrollable table — Revenue per country |
| 👤 **Agent Revenue Table** | Agent photo + Name + Revenue earned (with client images) |
| 📅 **Year Slicer** | Toggle between 2025, 2026, 2027 — entire dashboard filters dynamically |
| 📸 **Glimpses of Properties** | Carousel showing real property photos from the dataset |
| 📉 **Expenses by Quarter** | Area chart — Q1 to Q4 expense trend with values labeled |
| 📊 **Revenue by Month** | Bar chart — Monthly revenue with MAX (green) & MIN (red) highlighted using DAX |
| 🏆 **Top Selling Property** | Card showing the best-performing property with its actual photo |
| 💰 **KPI Cards (4)** | Revenue · Expenses · Profit · Sold Properties — with 3D icons |

---

## 🧮 DAX Measures Used

- **Revenue** = `SUM(Property_details[Price])`
- **Expenses** = `SUM(Property_details[Expense])`
- **Profit** = `[Revenue] - [Expenses]`
- **Sold Properties** = `COUNTROWS(FILTER(Property_details, Property_details[Status] = "Sold"))`
- **Max Revenue Month** = Used for conditional color formatting (green highlight)
- **Min Revenue Month** = Used for conditional color formatting (red highlight)
- **Top Selling Property** = `TOPN()` function for Top N card

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard building & publishing |
| **DAX (Data Analysis Expressions)** | Custom measures & calculations |
| **Power Query (M Language)** | Data transformation & cleaning |
| **GeoJSON / Shape Map** | Custom country-level map visualization |
| **Excel** | Calendar table & Customer data |
| **CSV** | Property raw data |

---

## 🚀 How to Run This Project

### Step 1 — Clone the Repository
```bash
git clone https://github.com/your-username/real-estate-powerbi-dashboard.git
cd real-estate-powerbi-dashboard
```

### Step 2 — Open the Dashboard
- Open **`Dashboard_Real_State.pbix`** in **Power BI Desktop** (free download from Microsoft)
- The dashboard will load with all visuals, slicers, and data pre-configured

### Step 3 — Explore the Dashboard
- Use the **year slicer** (2025 / 2026 / 2027) to filter all visuals at once
- Scroll through the **Country Revenue** and **Agent Revenue** tables
- Watch the **property image carousel** auto-scroll
- Hover over map countries to see revenue tooltips

### Step 4 — Learn Step by Step (Optional)
Follow the build journey using the numbered `.pbix` files:

| File | What You'll Learn |
|---|---|
| `1__Importing_data_and_slicers.pbix` | Data import, relationships, year slicers |
| `2__MAP_Visual.pbix` | Custom JSON Shape Map setup |
| `3__Bar_chart_and_max_min_formula.pbix` | Bar chart + MAX/MIN DAX highlight |
| `4__Top_N_Card_and_Metric.pbix` | Top N card + KPI metrics |
| `5__Line_Chart_and_carousel_chart.pbix` | Area chart + property image carousel |

---

## 🔍 Key Insights

- 🌏 Properties span **30 countries** across 5 continents
- 🏡 **82%** of all properties are successfully sold (69 out of 84)
- 📈 **June** is the peak revenue month in 2026 (3.8M); **May** leads in 2025 (4.0M)
- 💹 Profit improves year-over-year — **3M (2026) → 9M (2027)**
- 🏆 Top agents by revenue change each year — James Smith, Olivia Jones consistently high performers
- 📉 Expenses peaked in **Q2 of 2025** at 8.6M then stabilized

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

# 🚔 NYPD Crime Data Analysis & Visualization Pipeline

<div align="center">
  <img src="https://img.shields.io/badge/Azure-Data_Factory-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white"/>
  <img src="https://img.shields.io/badge/Snowflake-Data_Warehouse-29B5E8?style=for-the-badge&logo=snowflake&logoColor=white"/>
  <img src="https://img.shields.io/badge/Alteryx-Data_Profiling-FF6C2C?style=for-the-badge&logo=alteryx&logoColor=white"/>
  <img src="https://img.shields.io/badge/Tableau-Visualization-E97627?style=for-the-badge&logo=tableau&logoColor=white"/>
  <img src="https://img.shields.io/badge/Power_BI-Analytics-F2C811?style=for-the-badge&logo=power-bi&logoColor=black"/>
  <img src="https://img.shields.io/badge/NYC-Crime_Data-FF6B6B?style=for-the-badge"/>
</div>

## 📋 About This Project

**NYPD Crime Data Analysis Pipeline** is a comprehensive Business Intelligence solution that transforms New York City arrest data into actionable public safety insights. This project demonstrates advanced data engineering and analytics capabilities by processing **NYPD Arrest Data (Year-to-Date)** through sophisticated ETL workflows, dimensional modeling, and interactive dashboards to help NYC residents understand crime patterns and enhance public safety awareness.

## 🎯 Project Objectives

### **Public Safety Mission**
Safety is essential, and knowing what's happening around us is crucial. This project aims to help New York City residents get a comprehensive overview of crime patterns, trends, and safety insights through data-driven analysis and visualization.

### **What's in it for you?**
- **Dashboard Development Skills**: Appreciate the efforts that go into building sophisticated analytical dashboards
- **Data Profiling Expertise**: Understand the importance of profiling data, identifying inconsistencies, and making keen observations
- **ETL Pipeline Experience**: Learn the process of building staging data pipelines for ad-hoc analysis using SQL and prototype dashboards
- **Safety Intelligence**: Get helpful tips on safety before planning your next NYC trip through data-driven insights

## 🗃️ Data Source

### **NYPD Arrest Data (Year-to-Date)**
- **Source**: [NYPD Arrest Data](https://data.cityofnewyork.us/Public-Safety/NYPD-Arrest-Data-Year-to-Date-/uip8-fykc) - NYC Open Data Portal
- **Coverage**: Current year arrest records across all NYC boroughs
- **Key Attributes**: Arrest date, crime type, location, demographic information, precinct data
- **Geographic Scope**: All five NYC boroughs (Manhattan, Brooklyn, Queens, The Bronx, Staten Island)

## 🔍 Business Requirements & Analysis

### **Core Business Questions**

#### **📊 Time-Based Analysis**
1. **Temporal Patterns**: How many arrests occurred on any specific day, week, month, quarter, or year?
2. **Peak Activity**: What are the peak days and months for arrests?

#### **🔍 Crime Patterns & Trends**
3. **Crime Frequency**: What are the top 5 most frequently occurring crimes?
4. **Trend Analysis**: Which crimes have increased or decreased the most over time?

#### **🗺️ Geographic Analysis**
5. **Precinct Performance**: Are there specific precincts with higher felony arrests compared to misdemeanors?
6. **Borough Comparison**: Which borough has the highest number of arrests?

#### **👥 Demographic Analysis**
7. **Arrestee Demographics**: What is the distribution of arrestees by age, race, and gender?

#### **🔮 Predictive Insights**
8. **Crime Prediction**: Can we predict high-crime areas based on past arrest data?

### **Data-Driven Approach**
Each business question is analyzed against the dataset structure to ensure relevance and feasibility. Questions found to be irrelevant are documented with clear justifications and alternative SQL-based analytical approaches.

## 🏗️ Technical Architecture

### **Dimensional Modeling Framework**

#### **Business Analysis Questions Framework**
- **What?** - Crime types, arrest details, charges
- **When?** - Arrest dates, time patterns, seasonal trends
- **Where?** - Precincts, boroughs, geographic coordinates
- **Who?** - Arrestee demographics, age groups, gender, race
- **Why?** - Crime categories, offense levels, legal classifications

#### **Star Schema Design**
```
           DIM_DATE
               |
    DIM_CRIME ─── FACT_ARRESTS ─── DIM_LOCATION
               |                        |
          DIM_DEMOGRAPHICS        DIM_PRECINCT
                                       |
                                 DIM_BOROUGH
```

#### **Fact and Dimension Identification**
- **Fact Table**: `FACT_ARRESTS` - Core arrest events with measures
- **Dimension Tables**: 
  - `DIM_DATE` - Time hierarchy (day, week, month, quarter, year)
  - `DIM_CRIME` - Crime classifications and offense levels
  - `DIM_LOCATION` - Geographic information and coordinates
  - `DIM_DEMOGRAPHICS` - Arrestee age, race, and gender
  - `DIM_PRECINCT` - Police precinct details and jurisdictions
  - `DIM_BOROUGH` - NYC borough information

### **Grain Definition**
**Grain**: One record per arrest event, capturing individual arrest details at the most granular level including date, time, location, crime type, and arrestee demographics.

## 🔧 Data Processing Pipeline

### **Phase 1: Data Profiling & Analysis**

#### **Alteryx Data Profiling**
- **Data Quality Assessment**: Comprehensive profiling of CSV dataset
- **Missing Value Analysis**: Identification and documentation of data gaps
- **Data Consistency Review**: Detection of inconsistencies and anomalies
- **Cleaning Strategy**: Documentation of required data cleaning approaches

#### **Data Quality Challenges**
- **Missing Values**: Incomplete demographic information and location data
- **Inconsistent Formats**: Varying date formats and text inconsistencies
- **Data Validation**: Verification of precinct codes and borough mappings
- **Standardization**: Normalization of crime classifications and descriptions

### **Phase 2: ETL Pipeline Development**

#### **Azure Data Factory Implementation**
```
📥 Input: CSV Dataset (NYPD Arrest Data)
    ↓
🔧 Data Cleaning & Transformation
    ↓
🗃️ Stage Table in Snowflake Database
    ↓
📊 Dimensional Model Population
    ↓
🎯 Analytics-Ready Data Warehouse
```

#### **Staging Pipeline Components**
- **Data Ingestion**: Automated CSV data loading from NYC Open Data
- **Data Cleaning**: Standardization and validation processes
- **Data Transformation**: Business rule application and format conversion
- **Data Loading**: Efficient population of Snowflake staging tables

## 📊 Dashboard Development

### **Dual-Platform Visualization Strategy**

#### **Tableau Dashboards**
- **Interactive Crime Maps**: Geographic visualization of arrest patterns
- **Time Series Analysis**: Trend analysis with drill-down capabilities
- **Demographic Insights**: Population-based arrest distribution analysis
- **Comparative Analytics**: Borough and precinct performance comparisons

#### **Power BI Analytics**
- **Executive Dashboards**: High-level crime statistics and KPIs
- **Operational Reports**: Precinct-level performance metrics
- **Predictive Analytics**: Trend forecasting and pattern recognition
- **Mobile-Responsive**: Accessible insights for field personnel

### **📈 Key Visualizations**

#### **Time-Based Analysis Dashboard**
- **Daily/Weekly/Monthly Patterns**: Arrest volume trends across time periods
- **Seasonal Analysis**: Peak crime periods and cyclical patterns
- **Year-over-Year Comparisons**: Historical trend analysis
- **Real-time Monitoring**: Current period performance tracking

#### **Crime Pattern Analytics**
- **Top 5 Crime Types**: Most frequent offenses with trend indicators
- **Crime Evolution**: Increasing/decreasing crime categories over time
- **Severity Analysis**: Felony vs. misdemeanor distribution
- **Offense Classification**: Detailed crime category breakdowns

#### **Geographic Intelligence**
- **Borough Performance**: Arrest distribution across NYC boroughs
- **Precinct Analysis**: High-activity precincts and crime hotspots
- **Heat Maps**: Geographic concentration of criminal activity
- **Patrol Route Optimization**: Data-driven deployment strategies

#### **Demographic Insights**
- **Age Distribution**: Arrestee age patterns and generational trends
- **Racial Demographics**: Arrest patterns across racial categories
- **Gender Analysis**: Crime type distribution by gender
- **Cross-Demographic Correlations**: Multi-dimensional demographic analysis

#### **Predictive & Preventive Analytics**
- **Crime Hotspot Identification**: Historical pattern-based predictions
- **Resource Allocation**: Data-driven patrol deployment recommendations
- **Trend Forecasting**: Projected crime patterns and seasonal adjustments
- **Risk Assessment**: High-crime area identification and prevention strategies

## 🏆 Business Impact & Public Safety Value

### **🎯 Community Safety Outcomes**
- **Crime Awareness**: Enhanced public understanding of neighborhood safety patterns
- **Prevention Strategy**: Data-driven insights for crime prevention initiatives
- **Resource Optimization**: Efficient allocation of police resources based on patterns
- **Public Engagement**: Transparent crime data access for community involvement

### **📈 Operational Excellence**
- **Real-time Intelligence**: Current crime pattern monitoring and alerts
- **Performance Metrics**: Precinct and borough-level effectiveness tracking
- **Trend Analysis**: Long-term crime pattern identification and response
- **Predictive Policing**: Proactive crime prevention through data analytics

### **🌍 Strategic Advantages**
- **Evidence-Based Policing**: Data-driven law enforcement strategies
- **Community Trust**: Transparent crime reporting and public access
- **Policy Development**: Informed decision-making for public safety policies
- **Tourism Safety**: Crime pattern insights for visitor safety recommendations

## 🚀 Technology Stack

### **Data Engineering & Analytics**
- **🔧 ETL Processing**: Azure Data Factory for automated data pipelines
- **🗃️ Data Warehouse**: Snowflake for scalable data storage and processing
- **📊 Data Profiling**: Alteryx for comprehensive data quality analysis
- **🎨 Visualization**: Tableau and Power BI for interactive dashboards
- **☁️ Cloud Platform**: Microsoft Azure ecosystem for enterprise deployment

### **Data Processing Capabilities**
- **Automated ETL**: Scheduled data processing and updates
- **Real-time Analytics**: Near real-time crime pattern monitoring
- **Scalable Architecture**: Handling large volumes of arrest data
- **Multi-platform Integration**: Seamless data flow across tools

## 📁 Repository Structure

```
📂 NYPD-Crime-Data-Analysis/
├── 📊 data-profiling/
│   ├── alteryx-workflows/
│   ├── data-quality-reports/
│   └── profiling-documentation/
├── 🗃️ dimensional-model/
│   ├── logical-model/
│   ├── physical-model/
│   └── ddl-scripts/
├── 🔧 etl-pipeline/
│   ├── azure-data-factory/
│   ├── staging-scripts/
│   └── transformation-logic/
├── 📊 dashboards/
│   ├── tableau-workbooks/
│   ├── powerbi-reports/
│   └── visualization-assets/
├── 📖 documentation/
│   ├── business-requirements/
│   ├── technical-specifications/
│   └── user-guides/
└── 📋 README.md
```

## 🚀 Getting Started

### **Prerequisites**
- Azure subscription with Data Factory access
- Snowflake data warehouse instance
- Alteryx Designer for data profiling
- Tableau Desktop/Server for visualization
- Power BI Desktop/Service for analytics

### **Installation & Setup**

1. **Clone Repository**
```bash
git clone https://github.com/Pagar-Bhagyashri/NYPD-Crime-Data-Analysis.git
cd NYPD-Crime-Data-Analysis
```

2. **Download NYPD Dataset**
   - Access [NYPD Arrest Data](https://data.cityofnewyork.us/Public-Safety/NYPD-Arrest-Data-Year-to-Date-/uip8-fykc)
   - Download current year-to-date arrest data

3. **Review Technical Implementation**
   - Examine Alteryx workflow (`Bhagyashri_Pagar_Individual_Project_1.yxmd`)
   - Review Azure Data Factory pipeline (`NYPD_Arrest_Data_Pipeline.json`)
   - Check Snowflake database scripts (`NYPD_ARREST_DATA_SNOWFLAKE_SCRIPT`)

4. **Build Dimensional Model**
   - Execute Snowflake DDL scripts for table creation
   - Load cleaned dataset (`Cleaned_NYPD_Arrest_Data_Parquet_Bhagyashri_Pagar.parquet`)
   - Validate dimensional model relationships

5. **Deploy Analytics Dashboards**
   - Review Power BI visualization report
   - Configure dashboard connections to Snowflake
   - Set up automated refresh schedules

## 🔍 Key Insights & Safety Intelligence

### **Crime Pattern Discoveries**
- **Peak Crime Hours**: Identification of high-activity time periods
- **Seasonal Trends**: Monthly and quarterly crime pattern variations
- **Geographic Hotspots**: Precinct-level crime concentration analysis
- **Demographic Correlations**: Age, race, and gender arrest pattern insights

### **Public Safety Recommendations**
- **Neighborhood Safety**: Area-specific crime awareness and prevention tips
- **Travel Planning**: Safe route recommendations based on crime data
- **Community Engagement**: Crime prevention through neighborhood awareness
- **Emergency Preparedness**: High-risk area identification and response strategies

### **Law Enforcement Intelligence**
- **Resource Deployment**: Optimal patrol allocation based on crime patterns
- **Crime Prevention**: Proactive policing strategies using predictive analytics
- **Performance Monitoring**: Precinct effectiveness tracking and improvement
- **Policy Development**: Evidence-based crime prevention policy recommendations


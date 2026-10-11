
#  Large-Scale Data Analytics Using Hadoop, HDFS, and MapReduce

##  Project Overview

This project explores how organizations process and analyze large-scale datasets using Big Data concepts and technologies.

The project uses Python, Pandas, NumPy, Matplotlib, and Seaborn to analyze a real-world NYC Yellow Taxi trip dataset. It demonstrates data cleaning, exploratory data analysis (EDA), KPI calculation, data aggregation, visualization, and MapReduce-style processing.

The project also explains how **Hadoop, HDFS, and MapReduce** support distributed storage and processing of large datasets.

##  Objectives

- Understand the challenges of large-scale data processing.
- Explore the fundamentals of Hadoop, HDFS, and MapReduce.
- Analyze a real-world transportation dataset.
- Clean and preprocess data using Python.
- Calculate important business KPIs.
- Create charts and visualizations to identify patterns.
- Demonstrate MapReduce concepts using mapper and reducer logic.
- Generate reports and export analytical results.
- Understand the differences between traditional data processing and distributed processing.

##  Technologies Used

- **Python** – Programming and analysis
- **Google Colab** – Cloud-based development environment
- **Pandas** – Data cleaning and manipulation
- **NumPy** – Numerical computations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **PyArrow** – Parquet file support
- **Hadoop** – Distributed data processing framework
- **HDFS** – Hadoop Distributed File System
- **MapReduce** – Distributed processing programming model
- **GitHub** – Project documentation and version control

##  Dataset

**Dataset:** NYC Yellow Taxi Trip Records

**Data source:** NYC Taxi & Limousine Commission

Dataset download:

https://d37ci6vzurychx.cloudfront.net/trip-data/yellow_tripdata_2024-01.parquet

The dataset contains taxi trip information, including pickup and drop-off times, trip distance, fare amount, passenger count, payment details, and other trip-related attributes.

**Format:** Parquet

**Period analyzed:** January 2024

> Note: The number of records analyzed depends on the downloaded dataset and the cleaning steps performed in the notebook.

##  Project Architecture

```text
                 NYC Yellow Taxi Dataset
                           |
                           v
                   Data Collection
                           |
                           v
                    Data Cleaning
                           |
                           v
                Exploratory Data Analysis
                           |
                           v
                   KPI Calculation
                           |
                           v
                 MapReduce-Style Logic
                           |
                           v
                  Data Aggregation
                           |
                           v
                  Visualization
                           |
                           v
                 Reports and Insights
````

##  Project Workflow

### 1. Data Collection

* Download the NYC Yellow Taxi dataset.
* Load the Parquet file into Google Colab.
* Inspect the dataset structure and data types.

### 2. Data Cleaning

* Check for missing values.
* Identify duplicate records.
* Handle invalid and inconsistent values.
* Convert timestamp columns into appropriate date-time formats.
* Remove records that do not meet the selected analysis criteria.

### 3. Exploratory Data Analysis (EDA)

Analyze the dataset to understand:

* Trip distribution.
* Trip distance patterns.
* Fare amount distribution.
* Pickup and drop-off time patterns.
* Daily trip trends.
* Revenue patterns.

### 4. KPI Calculation

Calculate relevant analytical metrics, such as:

* Total Trips
* Total Fare Revenue
* Average Fare per Trip
* Average Trip Distance
* Average Trip Duration
* Total Passenger Count
* Daily Trip Count

The exact KPIs depend on the available columns and the cleaning rules used.

### 5. MapReduce-Style Processing

Demonstrate the basic MapReduce workflow.

**Map Phase:**

* Extract relevant fields from the cleaned dataset.
* Group records using a key, such as trip date.
* Emit key-value pairs.

**Shuffle and Group Phase:**

* Group records that share the same key.

**Reduce Phase:**

* Aggregate values for each key.
* Calculate daily trip counts or revenue totals.

**Important:** The notebook demonstrates MapReduce-style aggregation using Python. It does not, by itself, prove that a Hadoop cluster or HDFS was running. Actual Hadoop execution requires a configured Hadoop environment.

### 6. Data Visualization

Create charts to identify useful patterns and trends.

Expected visualizations include:

* Daily Trip Count
* Daily Fare Revenue
* Trip Distance Distribution
* Fare Amount Distribution
* Trips by Hour of Day

### 7. Report Generation

The notebook generates analytical outputs that may include:

* Cleaned dataset
* KPI summary
* Daily aggregation files
* Visualization images
* Analytical report
* Downloadable ZIP containing generated outputs

These files become available after the notebook runs successfully.

##  Key Performance Indicators (KPIs)

| KPI                | Description                                                |
| ------------------ | ---------------------------------------------------------- |
| Total Trips        | Number of trips included in the analysis                   |
| Total Fare Revenue | Sum of the selected fare or revenue field                  |
| Average Fare       | Average value of the selected fare field per trip          |
| Average Distance   | Average trip distance                                      |
| Average Duration   | Average trip duration where valid timestamps are available |
| Daily Trips        | Number of trips recorded per day                           |
| Daily Revenue      | Aggregated fare or revenue by day                          |

> Note: Fare amount and total trip amount are different measures. The project should specify which column is used for each revenue calculation.

## 🐘 Understanding Hadoop, HDFS, and MapReduce

### Hadoop

Apache Hadoop is a framework designed to store and process large datasets across multiple computers.

### HDFS

Hadoop Distributed File System (HDFS) stores files across multiple machines by splitting them into blocks and distributing those blocks across the cluster.

### MapReduce

MapReduce is a programming model for processing data in parallel.

It involves:

1. **Map:** Process input records and generate key-value pairs.
2. **Shuffle and Sort:** Group values by key.
3. **Reduce:** Combine grouped values to produce final results.

### Example

Suppose the input data contains:

| Date       | Fare |
| ---------- | ---: |
| 2024-01-01 |   10 |
| 2024-01-01 |   15 |
| 2024-01-02 |   20 |

The MapReduce-style aggregation produces:

| Date       | Total Fare |
| ---------- | ---------: |
| 2024-01-01 |         25 |
| 2024-01-02 |         20 |

This example illustrates aggregation by key. It is not a claim that Hadoop executed the calculation.

##  Project Structure

```text
Large_Scale_Data_Analytics_Hadoop/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── Large_Scale_Data_Analytics_Hadoop.ipynb
│
├── src/
│   ├── mapper.py
│   └── reducer.py
│
├── charts/
│   └── Generated visualization images
│
├── outputs/
│   └── Generated CSV and JSON files
│
├── reports/
│   └── Generated analytical report
│
└── docs/
    └── project_report_template.md
```

##  How to Run the Project

### Step 1: Open Google Colab

Visit:

https://colab.research.google.com/

### Step 2: Upload the Notebook

Upload:

`notebooks/Large_Scale_Data_Analytics_Hadoop.ipynb`

### Step 3: Install Dependencies

Run the following command in a notebook cell if the required libraries are not already installed:

```python
!pip install pandas numpy matplotlib seaborn pyarrow
```

### Step 4: Run the Notebook

Execute the notebook cells in order.

The notebook will download the dataset, process the data, calculate KPIs, generate charts, perform MapReduce-style aggregation, and prepare report files.

### Step 5: Download the Results

Download the generated output files from Google Colab.

Depending on the notebook implementation, these may include CSV files, JSON summaries, PNG charts, a Markdown report, and a ZIP archive.

### Step 6: Upload the Project to GitHub

1. Create a new GitHub repository.
2. Upload the notebook and project source files.
3. Run the notebook and generate the actual output files.
4. Add the generated charts and report to the repository.
5. Update this README with verified findings and actual results.
6. Commit and push the changes.

##  Expected Outcomes

After completing the project, you should be able to:

* Perform data cleaning on a real-world dataset.
* Conduct exploratory data analysis.
* Calculate analytical KPIs.
* Create meaningful data visualizations.
* Aggregate records using MapReduce-style logic.
* Explain the purpose of Hadoop and HDFS.
* Understand why distributed processing can help with large datasets.
* Generate reports and prepare project outputs for GitHub.

##  Traditional Processing vs. Distributed Processing

| Feature              | Traditional Processing                  | Distributed Processing                                        |
| -------------------- | --------------------------------------- | ------------------------------------------------------------- |
| Computing            | Usually relies on one machine           | Uses multiple machines                                        |
| Storage              | Local or centralized storage            | Data can be distributed across machines                       |
| Scalability          | Limited by available resources          | Can scale by adding cluster resources                         |
| Processing           | May become slow for very large datasets | Supports parallel processing                                  |
| Fault Tolerance      | Depends on the system design            | Distributed frameworks can provide fault-tolerance mechanisms |
| Example Technologies | Python, Pandas, SQL                     | Hadoop, HDFS, MapReduce                                       |

The performance advantage of distributed processing depends on dataset size, hardware, configuration, and workload. Distributed systems also introduce setup and coordination overhead.

##  Limitations

* The project uses a selected monthly dataset rather than the entire NYC Taxi data collection.
* Processing is performed in Google Colab unless a separate Hadoop environment is configured.
* The Python MapReduce-style implementation is an educational demonstration.
* Actual Hadoop and HDFS performance has not been benchmarked unless a real cluster is configured and tested.
* Findings are limited to the available dataset, selected columns, and data-cleaning rules.

##  Future Enhancements

* Configure a real Hadoop environment.
* Store the dataset in HDFS.
* Run the mapper and reducer using Hadoop Streaming.
* Compare Python processing time with Hadoop processing time.
* Analyze multiple months of taxi records.
* Explore Apache Spark for distributed data processing.
* Create an interactive dashboard using Power BI or Streamlit.
* Add automated data-quality checks.
* Improve report generation and visualization.

##  Conclusion

This project demonstrates a data analytics workflow using a real-world transportation dataset. It combines data cleaning, exploratory analysis, KPI calculation, visualization, and MapReduce-style aggregation.

It also introduces the roles of Hadoop, HDFS, and MapReduce in large-scale data processing and explains how distributed computing differs from traditional single-machine analysis.

The project provides a foundation for further learning in Big Data Analytics and distributed data engineering.

##  Author

**Jahnavi Adari**

B.Tech Student | Computer Science and Engineering – Data Science

Interests: Data Analytics, Python, SQL, Big Data, and Data Visualization

---

 If you find this project useful, consider giving the repository a star!

```

**How to use it:** Copy the Markdown content inside the code block into your `README.md` file. The `#` symbols create headings, `-` creates bullet points, `**text**` makes text bold, and triple backticks format code blocks.


# 🎬 Movie Recommendation & Analytics System using Hadoop

A big-data powered movie recommendation and analytics platform built using the Hadoop ecosystem.  
This project leverages distributed storage and batch processing techniques to analyze large-scale movie datasets and generate meaningful insights such as genre-based recommendations, popularity trends, and actor/movie analytics.

---

# Features

- 📂 Distributed movie dataset storage using HDFS
- ⚡ Batch data processing with Hadoop MapReduce
- 🧠 Genre-based movie recommendation system
- 📊 Rating-wise popularity analysis
- 🎭 Actor and movie collection evaluation
- 🗄️ SQL-like querying using Hive analytical tables
- 🐧 Linux-based Hadoop environment setup

---

# Technologies Used

| Technology | Purpose |
|------------|---------|
| Hadoop | Distributed processing framework |
| HDFS | Distributed data storage |
| MapReduce | Large-scale batch data processing |
| Hive | Data warehousing & querying |
| Linux | Hadoop environment & execution |

---

# System Architecture

```text
Movie Dataset
      ↓
     HDFS
      ↓
 Hadoop MapReduce
      ↓
 Processed Data
      ↓
     Hive
      ↓
Analytics & Recommendations

# Functionalities
🎯 Movie Recommendation
Recommended movies based on genres and user preferences
Processed large movie datasets efficiently using MapReduce
📈 Popularity Analysis
Analyzed movie ratings and popularity trends
Identified highly rated and trending movies
🎭 Actor & Movie Analytics
Evaluated actor performance and movie collections
Generated insights from large-scale datasets
🧾 Hive Querying
Created analytical Hive tables
Performed SQL-style queries for insights and reporting

SETUP & EXECUTION

Clone Repository
git clone https://github.com/Divyanshug17/hadoop-movie-recommendation.git
cd hadoop-movie-recommendation

Start Hadoop Services
start-dfs.sh
start-yarn.sh

Create HDFS Directory
hdfs dfs -mkdir /movies

Upload Dataset to HDFS
hdfs dfs -put dataset/movies.csv /movies

Compile Java Files
javac -classpath `hadoop classpath` -d . MovieMapper.java MovieReducer.java M

Create JAR File
jar -cvf MovieRecommendation.jar *

Run MapReduce Job
hadoop jar MovieRecommendation.jar MovieDriver /movies /output

View Output
hdfs dfs -cat /output/part-r-00000

Open Hive
hive

Create Hive Table
CREATE TABLE movies (
    movieId INT,
    title STRING,
    genre STRING
)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
STORED AS TEXTFILE;

Load Data into Hive
LOAD DATA INPATH '/movies/movies.csv'
INTO TABLE movies;

Run Sample Query
SELECT genre, COUNT(*) AS total_movies
FROM movies
GROUP BY genre;

Stop Hadoop Services
stop-yarn.sh
stop-dfs.sh

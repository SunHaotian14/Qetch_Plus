# Various Similarity Measurements on Sketch-Querying Frameworks
CS8803-MDS Project
 
Time series data play a crucial role in many sectors, such as finance, healthcare, speech recognition, etc. Visualizing and eventually interacting with time series data enable users to perform concrete analytics and help them explore underlying features from various datasets. One of the most promising interactive approaches is matching patterns from the original time series based on users’ hand-drawn sketches. Qetch is a well-developped framework to achieve the "querying by sketching" functionality. To be more specific, Qetch recognizes time series patterns from massive datasets that share similar shapes with the time series sketches drawn by users’ hands. To obtain the optimal matching results, Qetch introduces three different distance metrics, i.e., 1) Qetch’s newly proposed distance, 2) dynamic time warping (DTW), and 3) Euclidean distance (ED).

![screenshot](https://github.com/dtl-nyuad/qetch/blob/resources/screenshot.png)

The matching process can be regarded as the key to the overall performance of the sketch-querying systems. However, human sketches can sometimes involve high complexity and imperfection, posing even more challenges to these matching algorithms’ performance indices, such as matching accuracy, computation time, fault tolerance, etc. Existing pattern matching algorithms, such as DTW and ED, harness conventional distance metrics for time series data. These methods can suffer from performance degradation when dealing with massive and complex time series datasets. Therefore, it necessitates integrating the sketch querying system with appropriate matching approaches such that the desired patterns can be matched accurately and presented to users quickly. Besides, since the target dataset can sometimes be massive, there may exist multiple matched patterns that correspond to a single hand-drawn sketch. Thus, it is essential to compare the relations among different time series so that the querying system can provide exhaustive results for users.
To overcome the challenges mentioned above in time-series data matching, we propose equipping the sketch-querying system with some state-of-the-art matching approaches that adopt novel distance metrics and are capable of identifying the relations among time-series data. We also compare the novel methods to the existing DTW and ED to explore the most suitable scenarios where the novel distance metrics come into play.

To validate the performance of the proposed method, we design several experiments to measure how well the querying system performs empowered by different distance metrics. To simulate the usage in different application scenarios, we also investigate the querying and matching performance on various time-series datasets, such as the 3W dataset and UC Riverside Time Series Dataset. Several evaluation metrics, such as precision, accuracy, recall, and F1 score, are reported and analyzed in different experimental cases. Some further discussions on related works are also presented.

Overall, this project highlights the concrete progress that time-series data distance metrics and the following matching algorithms have moved forward in the past several years. This project shows that such technical advancement in time-series data can fulfill real- world applications such as sketch querying and time series relation comparison.

## References

**[Expressive Time Series Querying with Hand-Drawn Scale-Free Sketches](https://dl.acm.org/citation.cfm?id=3173962)**
<br/>
<span style="font-size:80%">Miro Mannino, Azza Abouzied - CHI'18</span>

**[Qetch: Time Series Querying with Expressive Sketches](https://dl.acm.org/citation.cfm?id=3193547)**
<br/>
<span style="font-size:80%">Miro Mannino, Azza Abouzied - SIGMOD'18</span>

## Videos

- [ACM SIGCHI Teaser Video](https://www.youtube.com/watch?v=g4uI_TGl3UI)

- [Demo video](https://youtu.be/T11OS4qO1c4)

- [Short Demo video](https://youtu.be/LP-JL40jUBs)


## Repository content

This repository contains:

- Qetch's source code, contained in the folder `Server`

- The datasets we used to compute our user studies, and Qetch's performance evaluations are contained in the folder `Datasets`

- The collected queries from our crowd study are in the folder `Crowd-Study Data`

## Installation

The original project's backend has been developed using NodeJS and a front-end which includes many technologies, such as: AngularJS, D3, Bootstrap, Paper.js, Math.js, etc. It requires a PostreSQL database in order to store and load time series.

In order to run the project install the required dependencies with the following commands:

    bower install
    npm install

To run the server run the following command:

    npm start

Now the interface can be accessed from a browser at:

    http://localhost:2048/

### Configure Database (Not optional!)

Create a database and a user in your PostgreSQL database for Qetch. Open PostgreSQL interactive terminal with:

    psql

Now create a database and a user with:

    CREATE DATABASE qetchdb;
    CREATE USER qetchdb_user WITH ENCRYPTED PASSWORD 'qetchdb_user_password';
    GRANT ALL PRIVILEGES ON DATABASE qetchdb TO qetchdb_user;

Now you can exit the interactive terminal and double-check that you can access this database 
using the specified username and password with:

    psql -U qetchdb_user -d qetchdb

You can report these settings in the file: `config.json` in order to allow Qetch to access this database.

In order to load the data to the database the scripts in the folder `Datasets` should be used. 
The script `load_all.sh` loads all the available datasets:

    cd Datasets/utils
    ./load_all.sh

Refresh the localhost page then you can see all default datasets have been loaded.

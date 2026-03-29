# COMP9336-Mobile-Data-Networking-Project-Data-Driven-Wi-Fi-Enhancement
Project Overview

This project analyses Wi-Fi network performance using real-world data collected from multiple locations at UNSW.
The goal is to understand retransmission behaviour, network congestion, and channel interference, and then evaluate machine learning models for predicting packet retransmissions.

Finally, potential protocol improvements are proposed based on the analysis results.

Data Collection
Locations

Data was collected from 5 different locations at UNSW:

Main Library
Electrical Engineering Building
J17 CSE Building
Science & Engineering Building
Law Library
Time Settings

Data was collected across 4 different days over two weeks:

Week 7

Friday (Weekend)
Sunday (Weekend)

Week 8

Tuesday (Weekday)
Wednesday (Weekday)

Each dataset:

Collected for 10+ minutes
Contains more than 10,000 retry packets
Channel Coverage

The analysis focuses on 2.4 GHz channels:

Channel 1
Channel 6
Channel 11

These channels were selected because they showed the highest network activity.

Data Processing

The cleaned dataset is stored in:

Clean_Wifi_data.csv

Due to system limitations, the data was processed directly using the CSV file instead of running the full data package.

Performance Analysis
Retransmission Analysis

The analysis compares retransmission patterns across:

Different locations
Day vs Night
Weekday vs Weekend
Different Wi-Fi channels

Key observations:

Science & Engineering building shows the highest retransmission overall.
Law Library has stable network usage because it operates 24 hours.
EE Building shows high retransmission during daytime due to heavy usage.
Network usage is generally higher during weekdays and daytime.

At night:

Network traffic decreases in most buildings.
However, retransmission remains high in locations near accommodation.
Channel Interference Analysis

Channels 1 and 11 show the highest interference levels, especially:

Wednesdays
Fridays
High traffic periods

Channel 6 is relatively more stable but still affected in some locations.

Overall conclusion:
Channel optimisation or dynamic channel selection could reduce retransmissions.

Network Performance Metrics

The following metrics were calculated:

Throughput
Total successfully transmitted packet length divided by total time.

Efficiency
Ratio of successfully transmitted data to total transmissions.

Retransmission Rate
Number of retransmitted packets divided by total transmissions.

Findings:

Throughput is generally stable across locations.
High retransmission can reduce effective throughput.
Network congestion affects performance during busy hours.
Latency Analysis

Packet delay was calculated based on the time difference between data packets and acknowledgements.

Results show:

Most packets have very low delay.
Majority of delays fall within 0–50 nanoseconds.
A small number of packets experience delays above 100 ns, caused by congestion or interference.

Nighttime latency is generally lower than daytime latency.

Machine Learning Evaluation

Three models were tested to predict retransmission:

k-Nearest Neighbours (kNN)
Random Forest
Logistic Regression
kNN Model

Non-retransmitted packets:
Precision: 0.96
Recall: 0.98
F1-Score: 0.97

Retransmission detection performance is weaker.

Overall accuracy:
0.94

Random Forest Model

Non-retransmitted packets:
Precision: 0.97
Recall: 0.98

Retransmitted packets:
Precision: 0.73
Recall: 0.59

Overall accuracy:
0.95

Random Forest performs more stable than kNN.

Logistic Regression

This model struggles to identify retransmitted packets accurately and is less reliable compared to the other models.

Model Interpretation

Important features affecting retransmission prediction:

Packet length
Noise level
Signal strength

Noise level and packet size are the most significant factors affecting retransmissions.

Proposed Protocol Enhancements
Dynamic Channel Allocation

The Wi-Fi system periodically scans channel congestion and switches to less crowded channels.

Benefits:

Reduced interference
Lower retransmission rate

Challenges:

Frequent switching may reduce stability.
Coordination between devices is required.
AI-Driven Traffic Prediction

Machine learning models can predict network traffic and allocate resources in advance.

Benefits:

Reduced congestion
Improved network efficiency

Challenges:

Requires real-time data processing
High computational cost

Suitable for:
Public Wi-Fi networks such as universities.

Reference

IEEE Journal on Selected Areas in Communications
https://www.comsoc.org/publications/journals/ieee-jsac

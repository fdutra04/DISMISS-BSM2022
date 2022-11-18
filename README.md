# DISMISS-BSM: detection of position spoofing in Basic Safety Messages

The technological evolution of vehicles, with the aggregation of sensors and communication capabilities, allowed the creation of intelligent transportation systems, which connect all traffic participants, including vehicles, pedestrians with their personal devices and even the transportation infrastructure itself, providing the exchange of information between vehicles, allowing safer navigation on the roads.
Cooperative driving becomes a reality with the establishment of Vehicle Ad Hoc Networks (VANETs), opening the Cooperative Intelligent Transportation System Era. The C-ITS use cases include (Static or dynamic) Platooning, Area reservation, Cooperative Merging, Cooperative Lane Change, and Cooperative Overtaking, among others. One of the main enablers of C-ITS applications is the Basic Safety Messages, which are signaling messages broadcasted frequently with necessary information regarding the vehicle's state, e.g., position, speed, heading, among others.
The security of vehicular communications is based on a public key infrastructure, which requires the vehicle to be authenticated on the network before being able to communicate, protecting the system from external attacks. However, nothing prevents a vehicle that is already authenticated on the network from being compromised and starting to misbehave. The Position forgery of BSMs in VANETs may lead to various traffic damages, such as route blocks, traffic jams, or even accidents. This work presents the DISMISS-BSM, an algorithm that can detect position spoofing in VANETs, resorting to four new features and a new way of grouping the messages in analysis windows of different sizes, from 2 to 23 BSMs, combining low latency and effectiveness in the misbehavior detection. We use five machine learning models to evaluate the DISMISS-BSM performance, showing remarkable results in detecting all attacks, surpassing other works in the area.

This repository contains the notebooks that were used for pre-processing the dataset and for building the detection models, as well as a link to an external repository that contains the CSV files that make up the VeReMi dataset.

This project was developed using Google's Colab and contains all the files necessary for its reproduction.

<!--ts-->
   * [Repository content](#repository-content)
   * [VeReMi dataset](#veremi-dataset)
<!--te-->

## Repository content

- `/preprocessing`: contains the notebooks used to combine the BSM and GPS information of each message received by the vehicles, in csv files; 
- `/models`: contains the notebooks used to configure and test the detection models conceived in this work.

## [VeReMi dataset](https://veremi-dataset.github.io/)

The [VeReMi dataset](https://veremi-dataset.github.io/) replicate several traffic scenarios in city of Luxembourg, utilizing the VEINS simulator,  encompassing 225 simulations, each containing a labeling file (ground truth) and a set of records of messages received by each vehicle that received messages.  The simulations have variations of three levels of vehicular density, three levels of attacker density, and five different types of attackers, and each combination of parameters was replicated five times, totaling 225 simulation rounds.  In addition, vehicle records have two types of messages, type 2 messages, vehicle telemetry data, and type 3 messages, containing Basic Safety Messages (BSM) data received from other vehicles by DSRC.

In order to facilitate the handling of the files and speed up the execution of the experiments, we transposed the VeReMi reports to .csv files, merging the type 2 (GPS) and 3 (BSM) messages. However, due to the size of the files, the resulting csv is stored in an [external repository](https://mega.nz/folder/5Bp2QCSY#TxAiyrJOmt9itJ12K6Lxlw).

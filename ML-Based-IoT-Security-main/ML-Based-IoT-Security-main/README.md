# Enhancing IoT Security using Machine Learning Based Network Traffic Analysis

In today's connected world, the rise of IOT devices in homes, increases the risk of cyber-attacks.
Our project introduces a smart system designed to detect these threats by monitoring network activity . 
The aim is to enhance the safety of our home networks by quickly identifying and addressing malicious activity, ensuring our system adapts to the constantly changing landscape of cybersecurity threats.

## Problem Statement

As smart home devices like bulbs,alexa and other IOT devices become more common, they increase the risk of cyber-attacks on home networks. 
Traditional security systems often fail to detect these threats in real time, putting personal data at risk. 
There's a critical need for an affordable, easy-to-use security solution that can analyze network traffic and spot potential threats quickly.
 
ML based Intrusion Detection System (IDS) offers a promising approach to protect home networks effectively without requiring users to have advanced technical knowledge. 
Machine Learning algorithms allows the model to learn the patterns in network traffic. Once trained, the model can be deployed with Raspberry Pi to analyze network traffic in real time.

## Approach / Solution
<img width="390" alt="Screenshot 2024-06-20 at 12 47 15 PM" src="https://github.com/Chakradhar-Punur/ML-Based-IoT-Security/assets/107631480/dc504498-a300-489a-a7b0-fa1cc6cc71f7">

1) Raspberry Pi and Smart Bulb: The process starts with a Raspberry Pi connected to a smart bulb. The Raspberry Pi is prepared with necessary hardware and initial connections.
2) Software Installation: Essential software is installed on the Raspberry Pi to facilitate the next steps, including tools for network monitoring and packet capture.
3) Packet Capture: The Raspberry Pi captures network traffic data from the smart bulb. This involves monitoring the interactions and communications between the smart bulb and the network.
4) Dataset Collection: The captured network packets are collected and organized into a dataset. This dataset comprises various features extracted from the network traffic.
5) Feature Selection: Important features are selected from the dataset using bio-inspired algorithms to ensure the most relevant data is used for analysis.
6) Machine Learning: Machine learning models are applied to the processed dataset to detect potential network attacks or anomalies, enhancing the security and performance of the smart bulb.

## Dataset Description

For creating the dataset, we connected Raspberry pi to monitor with Ubuntu installed on it and installed the smart bulb in the same network.
In normal scenario, we used tcpdump on the network to create the .pcap file which contained packets captured from the smart bulb using its IP address.
In Denial of Service(DoS) attack scenario, while using tcpdump to capture packets, we also used hping3 tool to flood the network by sending multiple SYN packets to the IP address of the bulb.
In Reconnaissance attack scenario, we used nmap tool to scan a target machine for the purpose of identifying information such as manufacturer, open ports, services actively running, and identifying the operating system version.
For the benchmark dataset, we used network traffic dataset from iot23 that contained over 1000000 packets.

## Code Snippets/Commands

DoS attack Command:
hping3 -c 10000000 -d 120 -S -w 64 -p 80 --flood --rand-source *victim IP address*

Reconnaissance attack Command:
nmap -sS -sU -T4 -A -v *victim IP address*

<img width="484" alt="Screenshot 2024-06-20 at 12 52 21 PM" src="https://github.com/Chakradhar-Punur/ML-Based-IoT-Security/assets/107631480/771dd115-49f7-4bc0-bdad-8e8655cd2061">

## Details of files in this repository

The csv files contain the dataset recorded by us using smart bulb and raspberry pi in various scenarios.
The .ipynb files contain the code where ML is performed on our dataset as well as on a benchmark dataset along with feature selection using bio inspired algorithms.

This ML model can then be deployed in raspberry pi in real time to predict attacks in a smart home environment.


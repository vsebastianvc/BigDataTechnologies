# Spark Streaming Sentiment analysis from API twitter

# Prerequisites
Be sure that you already has installed the next programs in your Cloudera Centos 6
-Kafka
-kafka-server
-Anaconda3 (python 3.5.1)
-All librarys (see below how...)

# Platform cloudera Centos 6
Check the service and see if hbase-master and  regionserver are up
service --status-all

# If Hbase is down run the next commands
sudo service hbase-regionserver start
sudo service hbase-master start

# Install kafka and run the next command
kafka-console-producer --broker-list localhost:9092 --topic projectTweets

# Create the environment
conda create -n py351 python=3.5.1

# To activate the environment run the next commands

source activate /home/cloudera/anaconda3/envs/py351

# To install the libraries run the next commands

pip install -r requirements.txt

# Create the Hbase
1)source activate /home/cloudera/anaconda3/envs/py351
2)python hbasetable.py 
3)from hbasetable import create_table
4)create_table()

# Create the Hive
Run the next hive file 
hive socialmediatable.hive

# SparkSQL
Run the next command in a console in your Cloudera virtual machine
spark-shell -i '/home/cloudera/Desktop/BigDataTechnologiesProject/sparkSQL.scala

#IMPORTANT in the class twitter.py is mandatory put the KEYS to connect with Twitter

# Run the daemons
1 python sparkstreaming.py
2 python twitter.py

Check the table socialmedia in HUE and that's all now we have the last tweets about of these 5 companies :)

## VISUALIZATION WITH PowerBI
1) Follow the guide "20181214_ConnectingMSPowerBI2Hive.docx"
2) Open the file "DashboardTweets.pbix" with PowerBI Desktop
3) Press "refresh" button and now you are ready to present to your boss :)

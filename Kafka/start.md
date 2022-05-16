.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

.\bin\windows\kafka-server-start.bat .\config\server.properties


.\bin\windows\kafka-topics.bat --create --topic quickstart-events --bootstrap-server localhost:9092


.\bin\windows\kafka-topics.bat --describe --topic quickstart-events --bootstrap-server localhost:9092

.\bin\windows\kafka-console-producer.bat --topic quickstart-events --bootstrap-server localhost:9092

## install kafka in ubuntu


sudo adduser kafka

sudo adduser kafka sudo

su -l kafka

mkdir ~/Downloads

curl "https://dlcdn.apache.org/kafka/3.1.1/kafka_2.13-3.1.1.tgz" -o ~/Downloads/kafka.tgz

sudo apt install openjdk-11-jre-headless

bin/zookeeper-server-start.sh config/zookeeper.properties &

bin/kafka-server-start.sh config/server.properties &


bin/kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092


bin/kafka-topics.sh --describe --topic quickstart-events --bootstrap-server kafkademopc.eastus.cloudapp.azure.com:9092


bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092



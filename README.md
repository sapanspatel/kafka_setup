# Kafka Setup MacOS

Follow the below steps to install kafka on your macOS. 


## STEP 1: GET KAFKA

[Download](https://www.apache.org/dyn/closer.cgi?path=/kafka/3.7.0/kafka_2.13-3.7.0.tgz) the latest Kafka release and extract it:

 

    $ tar -xzf kafka_2.13-3.7.0.tgz
    $ cd kafka_2.13-3.7.0

## STEP 2: START THE KAFKA ENVIRONMENT
##### Kafka with ZooKeeper

Run the following commands in order to start all services in the correct order:

```bash
# Start the ZooKeeper service
$ bin/zookeeper-server-start.sh config/zookeeper.properties
```
If you see error, it might be happening because of java setup. Follow step JAVA Error below.

Open another terminal session and run:
```bash
# Start the Kafka broker service
$ bin/kafka-server-start.sh config/server.properties
```

## STEP 3: RUN YOUR Project

Now run your project. It will only work if both zookeeper and broker service running. 


## STEP : JAVA Error
Open a new Terminal. 
First check if java is installed or not.

    $ java --version
If not installed then follow any java installation guide available online.

    # go to root directory
    $ cd ~/
    
    # List all the files in directory
    $ ls -la
    
    # Check if the .zshrc has JAVA_HOME Path
    $ cat .zshrc

If you don't see JAVA_HOME path in .zshrc then add it using below commands. Note it you have to replace the jdk directory according to your setup.

    $ cat >> .zshrc
    
    export JAVA_HOME=$HOME/OpenJDK/jdk-21.0.1.jdk/Contents/Home
  
    export PATH=$JAVA_HOME/bin:$PATH
     
Quit your terminal and restart new terminal and follow STEP 2 above to zookeeper. 

import.sh script will push data to tsdb table with tcollector for 1 sec interval. To import huge data, this process might be slow. This proccess need to transfer data through network connection using nc command which is infact slow.

To import bulk size data, I have tried import command of tsdb, which is awesome.
Step1: create a file with metricname, timestamp , value and tags for e.g

 r2time.load.test 946681204 30980 host=bikash
 r2time.load.test 946681205 24971 host=bikash

We can create this file with C, python or any other script, which is faster.

Step2: using command import to import file from step1

./tsdb import filename.txt --zkquorum=host.nameof.zookeeper

or if file is large use gzip to compress the file.
./tsdb import filename.gz --zkquorum=host.nameof.zookeeper

Step3: step2 import data successfully in the tsdb table, we can verify this looking at OpenTSDB web interface.


##Delete metrics from tsdb table.
./tsdb scan --delete --zkquorum=host.nameof.zookeeper 1973/01/01 min r2time.load.test

##Create metrics in openTSDB
./tsdb mkmetric r2time.load.test --zkquorum=host.nameof.zookeeper

##Transfer file to another node
nc -w 30 host.name.of.tsd 4242 > node2.txt


#!/bin/bash


METRIC="r2time.load.test" ##Name of metrics
#create metric with one second delay
for y in {2000..2013}
do
  for m in {01..12}
  do
    for d in {01..28}
    do
      for h in {0..23}
        do
	for min in {0..59}
         do
         for s in {0..59}
          do
            	HOUR=$h
                MINUTE=$min
                SECOND=$s
                #The date of the measure for example: DATE=$(date -d '1 november 2011' +'%Y-%m-%d')
                DATE_WH=$(date -d "$y-$m-$d $h:$min:$s" +"%Y-%m-%d %H:%M:%S")
                starttimestamp=$(date -d"$DATE_WH" +%s)
                VALUE=${RANDOM}
                echo $DATE_WH
                echo put $METRIC $starttimestamp $VALUE host=hostname  | nc -w 30  servername port
           done
         done
      done
    done
  done
done






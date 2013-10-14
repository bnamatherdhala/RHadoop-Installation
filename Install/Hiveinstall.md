## Hive Installation 


Please check Hive [compatible](http://hive.apache.org/releases.html) with for Hadoop version and [download](http://mirror.reverse.net/pub/apache/hadoop/common/stable/) it.

Log in as admin for sudo access

Download a hive tar.gz file by checking compatibility with Hadoop version (hive-x.x.x.tar.gz file. In my case it is hive-0.10.0.tar.gz)

Go to the downloaded directory and un-tar the file it will create a directory call hive-0.10.0.
```
  tar –xzf hive-0.10.0.tar.gz
```
Move directory hive-0.10.0 to /usr/local and change ownership to hduser using sudo access
```
  sudo mv hive-0.10.0 /usr/local
  sudo chown –R hduser:hadoop /usr/local/hive-0.10.0
```
Create soft-links to easy access for hive-0.10.0 directory 
```
  sudo ln –s /usr/local/hive-0.10.0 /usr/local/hive
```
Switch to hduser ```su hduser```

Set Hive environmental variable and alias in your bash shell config file(i.e. ~/.bashrc) by copy and paste below lines
Edit .bashrc file. 
```
  #setting up hive home path
  export HIVE_HOME=/usr/local/hive
  export PATH=$PATH:$HIVE_HOME/usr/local/hive
  #creating alias for start hive
  alias hvstart="cd /usr/local/hive/ && bin/hive"
  #creating alias for start hive thrift server mode
  alias hvsst="cd /usr/local/hive/ && bin/hive --service hiveserver"
```
Exit for the terminal and open a new terminal. Now you are ready to use hive

####How to check hive working right?

  * To start the hive cluster(make sure hadoop started already) ```hvstart```. It should show up a command prompt as "hive>"
  * Then type ```show tables;``` and then hit enter it should run properly without showing any errors. It will show “OK” since there is no preloaded table in hive
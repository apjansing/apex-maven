# Development Apache Apex Docker Image and Example MapReduce

## Abstract
Apache Apex is YARN-native framework for building distributed applications and applies native streaming to the data processing pipeline [[3]](#WEISE). The Apex project was mainly driven by the company DataTorrent. DataTorrent shut its doors back in May of 2018[[2]](#WIKI)[[7]](#DATANAMI).

This project is designed to help other developers write their own Apache Apex applications by providing a Docker image with Apex, JDK8, and Maven installed. The start-up script provided can be easily changed so that others can pass their project directory as a volume to a container and rapid testing can be performed.

## Example
### Starting Docker Container
To start the `apex` docker container,
```
git@github.com:apjansing/apex-maven.git
cd apex-maven/src/docker
./pull_and_start_dev_apex_docker.sh
```

### Running MapReduce
After the `apex` docker container is started,
```
cd src/MapReduce
mvn clean install
```

### Output
Once the Maven build finishes, you can see that the tests generated a `tmp` folder with an `output*` file. The `output*` file will have contents that look like,
```
{monstrous=1, allah=1, xlv=1, xxxvii=1, bag=1, dutch=1, xxiv=1, vii=3,...},
{... cheerless=1, monstrous=4, flinty=1, been=12, gaping=1, ...},
{... ticking=1, monstrous=1, been=64, mostly=2, ...},
{... account=5, monstrous=6, been=60, unquestion=1, ...}
```
Notice that the words _monstrous_, _been_, and other words repeatedly show up in separate jsons. That is as a result of how Apache Apex streams data and outputs the results of the DAG (Directed Acyclic Graph) object is saved after a time window.

## Resources
### Apex Documentations
* [Apex Docs](http://apex.apache.org/docs/apex)
* [Malhar Docs](http://apex.apache.org/docs/malhar)
* [Creating New Apex Project](http://apex.apache.org/docs/apex/apex_development_setup/#creating-new-apex-project)

### Github Repositories
* [Apex core](https://github.com/apache/apex-core)
* [Apex malhar](https://github.com/apache/apex-malhar)
* [Apex site](https://github.com/apache/apex-site)

### Apache Apex Downloads
* [Apex downloads](http://apex.apache.org/downloads.html)
* [Apex-Sandbox Image](https://hub.docker.com/r/apacheapex/sandbox/)
* [Apex Dev Image](https://hub.docker.com/r/apjansing/apex-maven/)

### Bibliography
<a name="APEX">[1]</a>Foundation, A. (2018). Apache Apex. [online] Apex.apache.org. Available at: https://apex.apache.org/ [Accessed 5 Nov. 2018].
  
  <a name="WIKI">[2]</a>En.wikipedia.org. (2018). Apache Apex. [online] Available at: https://en.wikipedia.org/wiki/Apache_Apex [Accessed 10 Nov. 2018].
  
  <a name="WEISE">[3]</a>Weise, T. (2016). Architectual Comparison of Apache Apex and Spark Streaming. [online] Available at: https://www.slideshare.net/ApacheApex/architectual-comparison-of-apache-apex-and-spark-streaming [Accessed 10 Nov. 2018].

  <a name="APEXrtd_dt">[4]</a>Dt-docs.readthedocs.io. (2018). Beginner's Guide - DataTorrent Documentation. [online] Available at: https://dt-docs.readthedocs.io/en/latest/beginner/ [Accessed 10 Nov. 2018].

  <a name="APEX-DOCS">[5]</a>Apex.apache.org. (2018). Apache Apex Documentation. [online] Available at: http://apex.apache.org/docs/apex/ [Accessed 10 Nov. 2018].

  <a name="MALHAR-DOCS">[6]</a>Apex.apache.org. (2018). Apache Apex Malhar Documentation. [online] Available at: http://apex.apache.org/docs/malhar [Accessed 10 Nov. 2018].

  <a name="DATANAMI">[7]</a>Leopold, G. (2018). DataTorrent, Stream Processing Startup, Folds. [online] Datanami. Available at: https://www.datanami.com/2018/05/08/datatorrent-stream-processing-startup-folds/ [Accessed 10 Nov. 2018].

  <a name="WEISE2">[8]</a>Weise, T. (2018). Stream Processing use cases and applications with Apache Apex | Big Data Spain. [online] Bigdataspain.org. Available at: https://www.bigdataspain.org/2016/program/fri-stream-processing-use-cases-applications-with-apache-apex.html [Accessed 12 Dec. 2018].

  <a name="CF">[9]</a>Yang, B. (2018). cloudfoundry-incubator/app-autoscaler. [online] GitHub. Available at: https://Github.com/cloudfoundry-incubator/app-autoscaler\#deploy-and-offer-auto-scaler-as-a-service [Accessed 12 Dec. 2018].

  <a name="APEX-JIRA">[10]</a>Issues.apache.org. (2018). Apache Apex Core - ASF JIRA. [online] Available at: https://issues.apache.org/jira/projects/APEXCORE/summary [Accessed 12 Dec. 2018]
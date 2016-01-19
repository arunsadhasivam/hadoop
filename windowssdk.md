
REASON for recompile with windows sdk:
=====================================
Hadoop source need to be recompiled with windows native sdk , the reason is hadoop
by default support linux. it does have native libraries as below. but in windows
need native windows libraries (dll) to support working. hence hadoop source
with version hadoop 2.3+ need to be downloaded and recompiled with windows sdk.


C:\hadoop-2.7.1\lib\native\libhadoop.so
C:\hadoop-2.7.1\lib\native\libhadooppipes.a
C:\hadoop-2.7.1\lib\native\libhdfs.so
C:\hadoop-2.7.1\lib\native\libhdfs.a
C:\hadoop-2.7.1\lib\native\libhadoop.so.1.0.0
C:\hadoop-2.7.1\lib\native\libhadooputils.a

other wise below error message will be thrown.


ISSUE IN DataNode:
=========================

ERROR1:
========
        DEPRECATED: Use of this script to execute hdfs command is deprecated.
        Instead use the hdfs command for it.
        16/01/20 00:27:25 ERROR util.Shell: Failed to locate the winutils binary in the
        hadoop binary path
        java.io.IOException: Could not locate executable C:\hadoop-2.7.1\bin\winutils.ex
        e in the Hadoop binaries.
                at org.apache.hadoop.util.Shell.getQualifiedBinPath(Shell.java:356)
                at org.apache.hadoop.util.Shell.getWinUtilsPath(Shell.java:371)
                at org.apache.hadoop.util.Shell.<clinit>(Shell.java:364)
                at org.apache.hadoop.util.StringUtils.<clinit>(StringUtils.java:80)
                at org.apache.hadoop.hdfs.server.datanode.DataNode.secureMain(DataNode.j
        ava:2483)
                at org.apache.hadoop.hdfs.server.datanode.DataNode.main(DataNode.java:25
        08)

ERROR2:
=======
STARTUP_MSG:   build = https://git-wip-us.apache.org/repos/asf/hadoop.git -r 15e
cc87ccf4a0228f35af08fc56de536e6ce657a; compiled by 'jenkins' on 2015-06-29T06:04
Z
STARTUP_MSG:   java = 1.7.0_79
************************************************************/
16/01/20 00:27:27 WARN util.NativeCodeLoader: Unable to load native-hadoop libra
ry for your platform... using builtin-java classes where applicable
16/01/20 00:27:29 FATAL datanode.DataNode: Exception in secureMain
java.lang.NullPointerException
        at java.lang.ProcessBuilder.start(ProcessBuilder.java:1010)
        at org.apache.hadoop.util.Shell.runCommand(Shell.java:483)
        at org.apache.hadoop.util.Shell.run(Shell.java:456)
        at org.apache.hadoop.util.Shell$ShellCommandExecutor.execute(Shell.java:
722)
        at org.apache.hadoop.util.Shell.execCommand(Shell.java:815)
        at org.apache.hadoop.util.Shell.execCommand(Shell.java:798)
        at org.apache.hadoop.fs.RawLocalFileSystem.setPermission(RawLocalFileSys
tem.java:728)
        at org.apache.hadoop.fs.FilterFileSystem.setPermission(FilterFileSystem.
java:502)
        at org.apache.hadoop.util.DiskChecker.mkdirsWithExistsAndPermissionCheck
(DiskChecker.java:140)
        at org.apache.hadoop.util.DiskChecker.checkDir(DiskChecker.java:156)
        at org.apache.hadoop.hdfs.server.datanode.DataNode$DataNodeDiskChecker.c
heckDir(DataNode.java:2344)
        at org.apache.hadoop.hdfs.server.datanode.DataNode.checkStorageLocations
(DataNode.java:2386)
        at org.apache.hadoop.hdfs.server.datanode.DataNode.makeInstance(DataNode
.java:2368)
        at org.apache.hadoop.hdfs.server.datanode.DataNode.instantiateDataNode(D
ataNode.java:2260)
        at org.apache.hadoop.hdfs.server.datanode.DataNode.createDataNode(DataNo
de.java:2307)
        at org.apache.hadoop.hdfs.server.datanode.DataNode.secureMain(DataNode.j
ava:2484)
        at org.apache.hadoop.hdfs.server.datanode.DataNode.main(DataNode.java:25
08)
16/01/20 00:27:29 INFO util.ExitUtil: Exiting with status 1
16/01/20 00:27:29 INFO datanode.DataNode: SHUTDOWN_MSG:
/************************************************************
SHUTDOWN_MSG: Shutting down DataNode at Arun-PC/192.168.1.103





Error in Namenode:
==================
ERROR 1:
=========
        DEPRECATED: Use of this script to execute hdfs command is deprecated.
        Instead use the hdfs command for it.
        16/01/20 00:27:25 ERROR util.Shell: Failed to locate the winutils binary in the
        hadoop binary path
        java.io.IOException: Could not locate executable C:\hadoop-2.7.1\bin\winutils.ex
        e in the Hadoop binaries.
                at org.apache.hadoop.util.Shell.getQualifiedBinPath(Shell.java:356)
                at org.apache.hadoop.util.Shell.getWinUtilsPath(Shell.java:371)
                at org.apache.hadoop.util.Shell.<clinit>(Shell.java:364)
                at org.apache.hadoop.util.StringUtils.<clinit>(StringUtils.java:80)
                at org.apache.hadoop.hdfs.server.common.HdfsServerConstants$RollingUpgra
        deStartupOption.getAllOptionString(HdfsServerConstants.java:80)
                at org.apache.hadoop.hdfs.server.namenode.NameNode.<clinit>(NameNode.jav
        a:248)
        16/01/20 00:27:25 INFO namenode.NameNode: STARTUP_MSG:
        /************************************************************
        STARTUP_MSG: Starting NameNode
        STARTUP_MSG:   host = Arun-PC/192.168.1.103
        STARTUP_MSG:   args = []
        STARTUP_MSG:   version = 2.7.1
        STARTUP_MSG:   classpath = C:\hadoop-2.7.1\etc\hadoop;C:\hadoop-2.7.1\share\hado
        op\common\lib\activation-1.1.jar;C:\hadoop-2.7.1\share\hadoop\common\lib\apached
        s-i18n-2.0.0-M15.jar;C:\hadoop-2.7.1\share\hadoop\common\lib\apacheds-kerberos-c
        odec-2.0.0-M15.jar;C:\hadoop-2.7.1\share\hadoop\common\lib\api-asn1-api-1.0.0-M2
        
        

ERROR 2:
========
        cond(s).
        6/01/20 00:27:26 INFO impl.MetricsSystemImpl: NameNode metrics system started
        6/01/20 00:27:26 INFO namenode.NameNode: fs.defaultFS is file:///
        6/01/20 00:27:27 WARN util.NativeCodeLoader: Unable to load native-hadoop libra
        y for your platform... using builtin-java classes where applicable
        6/01/20 00:27:29 ERROR namenode.NameNode: Failed to start namenode.
        ava.lang.IllegalArgumentException: Invalid URI for NameNode address (check fs.d
        faultFS): file:/// has no authority.
               at org.apache.hadoop.hdfs.server.namenode.NameNode.getAddress(NameNode.j
        va:471)
               at org.apache.hadoop.hdfs.server.namenode.NameNode.getAddress(NameNode.j
        va:461)
               at org.apache.hadoop.hdfs.server.namenode.NameNode.getRpcServerAddress(N
        meNode.java:512)
               at org.apache.hadoop.hdfs.server.namenode.NameNode.loginAsNameNodeUser(N
        meNode.java:612)
               at org.apache.hadoop.hdfs.server.namenode.NameNode.initialize(NameNode.j
        va:632)
               at org.apache.hadoop.hdfs.server.namenode.NameNode.<init>(NameNode.java:
        11)
               at org.apache.hadoop.hdfs.server.namenode.NameNode.<init>(NameNode.java:
        95)

ISSUE in YARN:
==============


yarn starts up without issues but below only one error.


STARTUP_MSG:   java = 1.7.0_79
************************************************************/
16/01/20 00:27:27 INFO conf.Configuration: found resource core-site.xml at file
/C:/hadoop-2.7.1/etc/hadoop/core-site.xml


16/01/20 00:27:27 WARN util.NativeCodeLoader: Unable to load native-hadoop libr
ry for your platform... using builtin-java classes where applicable

16/01/20 00:27:27 INFO security.Groups: clearing userToGroupsMap cache
16/01/20 00:27:28 INFO conf.Configuration: found resource yarn-site.xml at file
/C:/hadoop-2.7.1/etc/hadoop/yarn-site.xml


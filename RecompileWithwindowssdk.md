
REASON:
=======
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

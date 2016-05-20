# Hadoop-2.7.2-Windows-8-64-Bit-Version<br/>
Hadoop 2.7.2 windows version<br/><br/>

<b>Download and Install</b><br/><br/>

Download zip of master branch<br/><br/>

1. Extract downloaded zip to a folder (for example c:\hadoop)<br/>
2. Add environment variable HADOOP_HOME (c:\hadoop) and append %HADOOP_HOME%\bin to path environment variable<br/>
3. Create namenode and datanode directory under c:/hadoop/data/dfs/<br/><br/>

<b>Configure Hadoop</b><br/><br/>

Update following files to configure hadoop<br/><br/>

1. Copy and paste below code in file: C:\hadoop\etc\hadoop\core-site.xml<br/>
<p style="font-size:small"><br/>
<?xml version="1.0" encoding="UTF-8"?><br/><br/>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?><br/><br/>
<!--<br/>
  Licensed under the Apache License, Version 2.0 (the "License");<br/>
  you may not use this file except in compliance with the License.<br/>
  You may obtain a copy of the License at<br/><br/>
 
    http://www.apache.org/licenses/LICENSE-2.0<br/><br/>
 
  Unless required by applicable law or agreed to in writing, software<br/>
  distributed under the License is distributed on an "AS IS" BASIS,<br/>
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.<br/>
  See the License for the specific language governing permissions and<br/>
  limitations under the License. See accompanying LICENSE file.<br/>
--><br/>
 <!-- Put site-specific property overrides in this file. --><br/><br/>
 
&lt;configuration&gt;<br/> 
&lt;property&gt;<br/> 
&lt;name&gt;fs.defaultFS&lt;/name&gt; <br/> 
&lt;value&gt;hdfs://localhost:9000&lt;/value&gt; <br/> 
&lt;/property&gt; <br/> 
&lt;/configuration&gt;<br/> 
</p>

2. Copy and paste below code in file: C:\hadoop\etc\hadoop\hdfs-site.xml <br/><br/>
<p>
<?xml version="1.0" encoding="UTF-8"?><br/>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?><br/>
<!--<br/>
  Licensed under the Apache License, Version 2.0 (the "License");<br/>
  you may not use this file except in compliance with the License.<br/>
  You may obtain a copy of the License at<br/><br/>
 
    http://www.apache.org/licenses/LICENSE-2.0<br/><br/>
 
  Unless required by applicable law or agreed to in writing, software<br/>
  distributed under the License is distributed on an "AS IS" BASIS,<br/>
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.<br/>
  See the License for the specific language governing permissions and<br/>
  limitations under the License. See accompanying LICENSE file.<br/>
--><br/><br/>
 
<!-- Put site-specific property overrides in this file. --><br/><br/>
 
&lt;configuration&gt;<br/>
    &lt;property&gt;<br/>
        &lt;name&gt;dfs.replication&lt;/name&gt;<br/>
        &lt;value&gt;1&lt;/value&gt;<br/>
   &lt;/property&gt;<br/>
    &lt;property&gt;<br/>
        &lt;name&gt;dfs.namenode.name.dir&lt;/name&gt;<br/>
        &lt;value&gt;file:/hadoop/data/dfs/namenode&lt;/value&gt;<br/>
    &lt;/property&gt;<br/>
    &lt;property&gt;<br/>
        &lt;name&gt;dfs.datanode.data.dir&lt;/name&gt;<br/>
       &lt;value&gt;file:/hadoop/data/dfs/datanode&lt;/value&gt;<br/>
    &lt;/property&gt;<br/>
&lt;/configuration&gt;<br/><br/>
</p>
3. Copy and paste below code in file: C:\hadoop\etc\hadoop\yarn-site.xml <br/><br/>
<p>
<?xml version="1.0"?><br/>
<!--<br/>
  Licensed under the Apache License, Version 2.0 (the "License");<br/>
  you may not use this file except in compliance with the License.<br/>
  You may obtain a copy of the License at<br/><br/>
 
    http://www.apache.org/licenses/LICENSE-2.0<br/><br/>
 
  Unless required by applicable law or agreed to in writing, software<br/>
  distributed under the License is distributed on an "AS IS" BASIS,<br/>
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.<br/>
  See the License for the specific language governing permissions and<br/>
  limitations under the License. See accompanying LICENSE file.<br/>
--><br/>
&lt;configuration&gt;<br/>
    &lt;property&gt;<br/>
       &lt;name&gt;yarn.nodemanager.aux-services&lt;/name&gt;<br/>
      &lt;value&gt;mapreduce_shuffle&lt;/value&gt;<br/>
    &lt;/property&gt;<br/>
    &lt;property&gt;<br/>
       &lt;name&gt;yarn.nodemanager.aux-services.mapreduce.shuffle.class&lt;/name&gt;<br/>
      &lt;value&gt;org.apache.hadoop.mapred.ShuffleHandler&lt;/value&gt;<br/>
    &lt;/property&gt;<br/>
    &lt;property&gt;<br/>
       &lt;name&gt;yarn.application.classpath&lt;/name&gt;<br/>
      &lt;value&gt;<br/>
            %HADOOP_HOME%\etc\hadoop,<br/>
            %HADOOP_HOME%\share\hadoop\common\*,<br/>
            %HADOOP_HOME%\share\hadoop\common\lib\*,<br/>
            %HADOOP_HOME%\share\hadoop\mapreduce\*,<br/>
            %HADOOP_HOME%\share\hadoop\mapreduce\lib\*,<br/>
            %HADOOP_HOME%\share\hadoop\hdfs\*,<br/>
            %HADOOP_HOME%\share\hadoop\hdfs\lib\*,     <br/>     
            %HADOOP_HOME%\share\hadoop\yarn\*,<br/>
            %HADOOP_HOME%\share\hadoop\yarn\lib\*<br/>
       &lt;/value&gt;<br/>
    &lt;/property&gt;<br/>
&lt;/configuration&gt;<br/><br/>
</p>
4. Copy and paste below code in file: C:\hadoop\etc\hadoop\mapred-site.xml <br/><br/>
<p>
<?xml version="1.0"?><br/>
<?xml-stylesheet type="text/xsl" href="configuration.xsl"?><br/>
<!--<br/>
  Licensed under the Apache License, Version 2.0 (the "License");<br/>
  you may not use this file except in compliance with the License.<br/>
  You may obtain a copy of the License at<br/><br/>
 
    http://www.apache.org/licenses/LICENSE-2.0<br/><br/>
 
  Unless required by applicable law or agreed to in writing, software<br/>
  distributed under the License is distributed on an "AS IS" BASIS,<br/>
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.<br/>
  See the License for the specific language governing permissions and<br/>
  limitations under the License. See accompanying LICENSE file.<br/>
--><br/>
 <!-- Put site-specific property overrides in this file. --><br/>
 &lt;configuration&gt;<br/>
    &lt;property&gt;<br/>
       &lt;name&gt;mapreduce.framework.name&lt;/name&gt;<br/>
      &lt;value>yarn&lt;/value&gt;<br/>
    &lt;/property&gt;<br/>
&lt;/configuration&gt;<br/><br/>
</p>
<b>Format namenode</b><br/><br/>

Open command prompt and switch to haddop bin directory and execute following command<br/><br/>

c:\hadoop\bin>hdfs namenode -format<br/><br/>

<b>Start HDFS (Namenode and Datanode)</b><br/><br/>

c:\hadoop\sbin>start-dfs<br/><br/>
 
Namenode and Datanode each will be opened in new command prompt windows<br/><br/>

<b>Start MapReduce i.e. YARN</b><br/><br/>

c:\hadoop\sbin>start-yarn<br/><br/>

Resource Manager and Node Manager each will be opened in new command prompt windows<br/><br/>

<b>Validate Installation</b><br/><br/>

Open node manager with http://localhost:8042 and namenode with http://localhost:50070<br/><br/>

<b>Stop HDFS & MapReduce</b><br/><br/>

c:\hadoop\sbin>stop-dfs<br/><br/>
c:\hadoop\sbin>stop-yarn<br/><br/>

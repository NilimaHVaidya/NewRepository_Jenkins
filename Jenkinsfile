pipeline { 
2     agent { 
3         label "windows" 
4     } 
5     tools { 
6         maven 'Maven3.1.1' 
7         jdk 'java8' 
8     } 
9     stages { 
10         stage ('Initialize') { 
11             steps { 
12                 bat ''' 
13                     echo "PATH = %PATH%" 
14                     echo "M2_HOME = %M2_HOME%" 
15                 ''' 
16             } 
17         } 
18 
 
19         stage ('Build') { 
20             steps { 
21                     bat 'cd NumberGenerator & mvn install' 
22             } 
23              post { 
24                 success { 
25                     junit 'NumberGenerator/target/surefire-reports/*.xml' 
26                         } 
27                  } 
28                 
29 
 
30             
31             } 
32         } 
33      
34 } 

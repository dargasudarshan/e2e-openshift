### BF12-Verify application availablity when node is tainted due to disk-pressure taint.

#### Description

This test evicts a node due to disk-pressure taint and checks if the application is rescheduled and verify its availability.

#### Prerequisites

- OpenShift Cluster should be created and have the dependencies installed.
- cStor based storage pool should have been created.
- OpenEBS storage class should be created with the desired storage pool claim.

#### Procedure

- This job triggers the litmus experiments which evicts a node due to disk failure taint and verify of the application is scheduled on other node.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly.
- It deploys statefulset application consuming OpenEBS Volume and checks if the application is deployed successfully.
- Then it evicts a node where application is running and check if application is rescheduled and verify its availability.
- Finally, it deprovisions the statefulset application and update the result.

#### Expected result

- Application should be scheduled on some other node.

#### Test Result


| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
|     <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/23629">23629</a>           |  Taint the node where the application is running and check the behaviour           | Mon Apr 29 12:52:39 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:78feac387f83f9d260585f40300af47bb2fb1836,type:phrase),type:phrase,value:78feac387f83f9d260585f40300af47bb2fb1836),query:(match:(commit_id:(query:78feac387f83f9d260585f40300af47bb2fb1836,type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:1120,type:phrase),type:phrase,value:1120),query:(match:(pipeline_id:(query:1120,type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/21950">21950</a>           |  Taint the node where the application is running and check the behaviour           | Fri Apr 26 13:00:09 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:78feac387f83f9d260585f40300af47bb2fb1836,type:phrase),type:phrase,value:78feac387f83f9d260585f40300af47bb2fb1836),query:(match:(commit_id:(query:78feac387f83f9d260585f40300af47bb2fb1836,type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:1071,type:phrase),type:phrase,value:1071),query:(match:(pipeline_id:(query:1071,type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/21356">21356</a>           |  Taint the node where the application is running and check the behaviour           | Thu Apr 25 18:16:40 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:96f49645a1eaab775a5937b338bc97af9897a385,type:phrase),type:phrase,value:96f49645a1eaab775a5937b338bc97af9897a385),query:(match:(commit_id:(query:96f49645a1eaab775a5937b338bc97af9897a385,type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:1054,type:phrase),type:phrase,value:1054),query:(match:(pipeline_id:(query:1054,type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a> |
|     <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/21315">21315</a>           |  Taint the node where the application is running and check the behaviour           | Thu Apr 25 16:30:57 IST 2019  | <a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:96f49645a1eaab775a5937b338bc97af9897a385,type:phrase),type:phrase,value:96f49645a1eaab775a5937b338bc97af9897a385),query:(match:(commit_id:(query:96f49645a1eaab775a5937b338bc97af9897a385,type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:1050,type:phrase),type:phrase,value:1050),query:(match:(pipeline_id:(query:1050,type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a> |
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/21141">21141</a>   |  Taint the node where the application is running and check the behaviour           |  Thu Apr 25 14:24:56 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:d22a0e8006f4a6b54f130c52971f9fe096bf2fb1,type:phrase),type:phrase,value:d22a0e8006f4a6b54f130c52971f9fe096bf2fb1),query:(match:(commit_id:(query:d22a0e8006f4a6b54f130c52971f9fe096bf2fb1,type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:1045,type:phrase),type:phrase,value:1045),query:(match:(pipeline_id:(query:1045,type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a>  |
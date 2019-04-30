### CL2N-Creating snapshot for Jiva Volume

#### Description

The goal of this test is to ensure that the snapshot can be created for Jiva Volume successfully.

#### Prerequisites

- OpenShift Cluster should be created and have the dependencies installed.
- Jiva storage pool and storage class should be created. 

#### Procedure

- This job triggers the litmus experiments which checks if the Jiva volume snapshot can be created successfully.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest files accordingly.
- The first litmus experiment deploys busybox application with single Jiva volume replica.
- The next litmus experiment updates the snapshot template with the pvc and namespace values.
- It uses create-snapshot utility to create volume snapshot.
- Finally, the job checks if the snapshot is created successfully in all the associated storage pool pods.

#### Expected result

- The volume snapshot should be created successfully.

#### Test Result
| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/24716">24716</a>   |  Verify if the snapshot can be created for JIVA persistent volume           |  Tue Apr 30 14:45:36 IST 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:c433bc389f4dfe19167c230acbd9fa8530119871,type:phrase),type:phrase,value:c433bc389f4dfe19167c230acbd9fa8530119871),query:(match:(commit_id:(query:c433bc389f4dfe19167c230acbd9fa8530119871,type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:1155,type:phrase),type:phrase,value:1155),query:(match:(pipeline_id:(query:1155,type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a>  |
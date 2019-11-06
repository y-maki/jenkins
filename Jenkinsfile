node{
    stage('newapp'){
        openshift.withCluster() {
            openshift.withProject() {
                def webapp = openshift.newApp( 'quay.io/wildfly/wildfly-centos7:latest~https://github.com/hochi2808/traning-app-01.git' )
                echo "new-app created ${webapp.count()} objects named: ${webapp.names()}"
                openshift.expose("svc","traning-app-01")
                echo "Service exposed"
                webapp.describe()
            }
        }
    }
}

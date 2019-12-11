node('master') {
		checkout scm
    stage('Build') {
        sh label: '', script: 'mvn -Dmaven.test.failure.ignore clean package'
    }
    stage('Results') {
    	junit '**/target/surefire-reports/TEST-*.xml'
    	archive 'target/*.jar'
    }
}

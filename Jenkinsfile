pipeline {
    agent any
    stages {
        stage('Start Build') {
            steps {
                    echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage('checkout class scm') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], \
				doGenerateSubmoduleConfigurations: false, extensions: [], \
				submoduleCfg: [], userRemoteConfigs: [[credentialsId: \
				'be30ea9b-273c-4fce-b044-a06507e0a46b', url: 'https://github.com/obiomap/class.git']]])
            }
        }
        stage('deploy war to tomcat') {
            steps {
				sh 'echo "I will do this no matter what the status is"'
				sh 'cp $WORKSPACE/*.war /data/tomcat8/webapps'
            }
        }
    }
}

pipeline {
    agent { label 'master' }
    tools { 
        maven 'mymaven' 
    }
    stages {
	stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }    
        stage('scm') {
            steps {
                git 'https://github.com/ganeshlovesdevops/maven_demo.git'
            }
        }

    stage('build') {
        steps {
            sh 'mvn clean install'
        }
    }
    stage('deploy') {
        steps {
        //bat 'copy "C:\\Program Files (x86)\\Jenkins\\workspace\\raghuproject\\gameoflife-web\\target\\*.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps\\"'
            
		    sh 'cp /var/lib/jenkins/workspace/declarativepipeline/target/*.war /opt/tomcat/webapps/'
        }
    }
}
}

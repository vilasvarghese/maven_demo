pipeline {
    agent any
    stages {
    stage('build') {
    steps {
    def mvnhome = tool name: 'mymaven', type: 'maven'
    bat "${mvnhome}\\bin\\mvn clean install"
    }
}
    stage('junit') {
steps {
    junit healthScaleFactor: 10.0, testResults: '**/gameoflife-web/target/surefire-reports/*.xml'
    }
}
    stage('deploy') {
steps {
    bat 'copy "C:\\Program Files (x86)\\Jenkins\\workspace\\raghupipeline\\gameoflife-web\\target\\*.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps\\"'
    }
}
}
}

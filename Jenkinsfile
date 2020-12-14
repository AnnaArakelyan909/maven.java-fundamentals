pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            //args '-v /root/.m2:/root/.m2'
            args '-v $HOME/.m2:/var/maven/.m2:z -e MAVEN_CONFIG=/var/maven/.m2 -e MAVEN_OPTS="-Duser.home=/var/maven"'
        }
    }
    stages {
        stage('SCM Checkout') {
            steps {
                sh 'git clone https://github.com/AnnaArakelyan909/spring.jsp_loginpage.git'
            }
        }

        stage('Compile-Package') {
            steps {
            script{
                def mvnHome = tool name: 'maven-3', type: 'maven'
                sh "${mvnHome}/bin/mvn/package"
                }
            }
        }
    }
}

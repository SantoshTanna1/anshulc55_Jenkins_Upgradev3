pipeline {
      agent any
      stages {
            stage('Init') {
                  steps {
                        echo 'Hi, this is Anshul from LevelUp360'
                        echo 'We are Starting the Testing'
                  }
            }
            stage("audit") {
                  steps {
                        sh '''
                              mvn -version
                              git --version
                              java -version
                        '''
                  }
            }

            stage('UNit TESTS') {
                  steps {
                        dir('./java-tomcat-sample'){
                              sh '''
                              echo "testing unit tests"
                              mvn test
                              '''
                        }
                        echo 'Building Sample Maven Project'
                  }
            }
            stage('bUILD') {
                  steps {
                        echo "Building the application"
                        sh 'mvn -f java-tomcat-sample/pom.xml clean package'
                  }
            }
            stage('Deploy Production') {
                  steps {
                        echo "Deploying in Production Area"
                  }
            }
      }
}
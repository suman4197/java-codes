pipeline { 
    agent none 
        stages {
            stage ('Build') {
                agent {label 'slave01'}
                steps {
                   git branch: 'main', url: 'https://github.com/suman4197/java-codes.git'
                   sh 'mvn clean install'
                  echo "build is success"
                }
            }
            
           stage ('Deploy') {
                agent {label 'slave01'}
                steps {
                   sh 'cp -r /home/ec2-user/.m2/repository/com/efsavage/hello-world-war/1.0.0/hello-world-war-1.0.0.war /homr/ec2-user/test1'
                  echo "deploy is success"
                }
           }
           stage ('Test') {
                agent {label 'slave01'}
                steps {
                    echo "test is succesful"
                }
           }
            
       }
}

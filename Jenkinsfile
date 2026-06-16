pipeline{
        agent any
        tools{
              maven 'maven'
        }
        stages{
               stage('Checkout'){
               steps{
                     git branch: 'main',
                     url: 'https://github.com/dishacodes15/maventestjenkins.git'
                    }
               }
               stage('Build'){
               steps{
                     sh 'mvn clean package'
                    }
               }
               stage('test'){
               steps{
                     sh 'mvn test'
                    }
               }
               stage('Run Application'){
               steps{
                     sh 'java -jar target/mvntestjenkins-1.0-SNAPSHOT.jar'
                     }
                }
            }
post{
success{
echo 'build successful!!!'
}
failure{
echo 'build failed boohoo'
}
}
}

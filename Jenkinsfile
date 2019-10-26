pipeline{

   environment{
      BUILD_BRANCH = 'master'     
      GIT_URL = 'https://github.com/1046702/JenkinsRepo'
   }

   agent any

   stages{
      stage('Initialize'){
         steps{
            sh '''
               echo "PATH=${PATH}"   
           '''
         }
      }
      stage('clean workspace'){
         steps{
            cleanWs()
         }
      }
      stage('checkout'){
         steps{
            echo "CURRENT PWD: ${PWD}"
            sh "whoami"
            sh "ls"  
            echo "${PWD}"
            sh "cp ./VERSION '${WORKSPACE}'"
            git branch: "${env.BUILD_BRANCH}", credentialsId: "\$4Currency", url: "${env.GIT_URL}"
         }
      }
   }

}

pipeline 
 {
   
  stages {
   
           stage('checkout')
     		  {
                 steps {
                          echo "----Now I will try to dpeloy Lunar system----"  
                       }
              }
          stage('build')
         	  {
      
                   environment {
                                JOB_NAME = "${env.JOB_NAME}"
                               }
                   steps  {
                                timestamps() 
				                     {
										sh "pwd"
										sh "whoami"
										echo "current job name : Lunar system"

										sh """ kubectl  apply -f ./mydeploy.yaml """ 
                                               
                                                                                 sh """ kubectl  apply -f ./myservice.yaml """
              
                                     }
                          }           
              }
         }

	post {
		failure {
					echo "Execution failed unfortunately"							
				}
		}      
 }

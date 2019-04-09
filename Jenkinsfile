node {

   stage('Preparation') {
     pol scm// for display purposes
     sh 'ls'
     git 'https://github.com/Amarlanda/jenkins.git'
   }
   try {
          stage ('checkout'){
          git 'https://github.com/g0t4/jenkins2-course-spring-boot.git'


          def project_path = "spring-boot-samples/spring-boot-sample-atmosphere"
          dir(project_path) {

              stage 'compiling, test, packaging'

              sh 'mvn clean package'

              stage 'archival'
              step([$class: 'ArtifactArchiver',
                     artifacts: "target/*.jar",
                     excludes: null])

          }

          notify('Success')
      }//end of stage block

      } catch (err) {
          notify("Error ${err}")
          currentBuild.result = 'FAILURE'
      }

}

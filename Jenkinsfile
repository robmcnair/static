pipeline {
     agent any
     stages {
         stage('Lint HTML') {
             steps {
                  sh 'tidy -q -e *.html'
              }
         }       
         stage ('Upload to AWS') {
             steps {
                  withAWS(region:'us-east-2',credentials:'aws-static'){
                    s3Upload(file:'index.html', bucket:'robsudacityproject3', path:'http://robsudacityproject3.s3-website.us-east-2.amazonaws.com')
                  sh 'echo "Hello World"'
                  sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
                 }
             }
         }
     }
}

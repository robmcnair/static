pipeline {
     agent any
     stages {
         stage ('Upload to AWS') {
             steps {
                  withAWS(region:'us-east-2',credentials:'jenkins')
                  s3Upload(file:'index.html', bucket:'robsudacityproject3', path:'http://robsudacityproject3.s3-website.us-east-2.amazonaws.com/index.html')
                  sh 'echo "Hello World"'
                  sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
                 }
             }
         }
     }

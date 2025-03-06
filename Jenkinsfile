buildPlugin(
  useContainerAgent: true,
  configurations: [
    [platform: 'linux', jdk: 11],
    [platform: 'windows', jdk: 11],
])

 pipeline{
     agent any
     tools {
         jfrog 'jfrog-cli-01'
     }
     stages {
         stage ('Testing') {
              steps {
                  jf '-v' 
                  jf 'c show'
                  jf 'rt ping'
                  sh 'touch test-file'
                  jf 'rt u test-file jfrog-cli-01/'
                  jf 'rt bp'
                  jf 'rt dl jfrog-cli-01/test-file'
               }
          } 
      }
 }

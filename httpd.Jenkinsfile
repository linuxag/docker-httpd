pipeline{
  agent{label "worker1"}
   stages {
    stage("httpd build"){
     steps{
      sh '''
      docker build -t newhttpd -f httpd.Dockerfile .
      '''
      }
    }
    stage("httpd build"){
     steps{
      sh '''
      docker run -d -p 8190:80 --name newhttpd1 newhttpd
      '''
      }
    }
  }
}

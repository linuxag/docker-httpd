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
    stage("run"){
     steps{
      sh '''
      docker ps -a
      docker rm -f newhttpd | exit 0
      docker run -d -p 8190:80 --name newhttpd1 newhttpd
      '''
      }
    }
  }
}

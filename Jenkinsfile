pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'sh \'mvn package\''
      }
    }

    stage('dockerbuild') {
      steps {
        sh '''echo "from centos" > Dockerfile
echo "run yum install httpd -y" >> Dockerfile

docker build -t jjj .'''
      }
    }

    stage('deployent') {
      steps {
        sh 'docker run -itd --name con -p 99:80 jjj'
      }
    }

  }
}
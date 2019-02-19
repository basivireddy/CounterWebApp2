#!groovy
node(){
         stage 'Checkout'
            checkout scm
         docker.withRegistry('https://registry.hub.docker.com', 'docker-credentials'){
         stage 'Dockerbuild'
                echo 'Building docker image'
                  def app = docker.build "CounterWebApp:${env.BRANCH_NAME}-${env.BUILD_NUMBER}"
         stage 'Docker push'
            echo 'Pushing docker image to ECH'
                app.push()
        
  }
}

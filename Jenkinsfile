node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       app = docker.build("sushmanth98/test4")
    }

    stage('Test image') {
  

        app.inside {
            sh 'echo "Tests passed2"'
        }
    }

    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', '9fd24f2b-f7cc-4ee6-8e2e-9f4536cd52ff') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
     
        
     
}

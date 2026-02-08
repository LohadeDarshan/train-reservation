node {
    def imageName = "java-tomcat-app:1.0"
    def containerName = "tomcatapp"
    def appPort = "8081"

    stage("Checkout Code") {
        git branch: "master",
            url: "https://github.com/Saikeerthi-3/train-reservation.git"
    }

    stage("Build WAR") {
        sh "mvn clean package -DskipTests"
    }

    stage("Verify WAR") {
        sh "ls -l target/"
        sh "ls -l target/*.war"
    }

    stage("Build Docker Image") {
        sh "docker build -t ${imageName} ."
    }

    stage("Deploy Container") {
        sh """
        docker stop ${containerName} || true
        docker rm ${containerName} || true
        docker run -d --name ${containerName} -p ${appPort}:8080 ${imageName}
        docker ps
        """
    }

    stage("Test Application") {
        sh "sleep 15"
        sh "curl -I http://localhost:${appPort}/ || true"
    }
}

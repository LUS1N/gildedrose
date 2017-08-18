node {
    stage ('Preparation'){
        // echo "Clonning the repo."
        // checkout scm
        git credentialsId: '7aa69393-1e0f-477d-b74a-6147a56701d3', url: 'https://github.com/LUS1N/gildedrose.git'

    }
    stage ('Build'){
        // mvn clean package
        sh 'docker run -i --rm --name my-maven-project -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn install' 
    }
    stage ('Results'){
        echo 'Hello World'
    }
}
node {
    stage ('Preparation'){
        // echo "Clonning the repo."
        // checkout scm
        git credentialsId: '7aa69393-1e0f-477d-b74a-6147a56701d3', url: 'https://github.com/LUS1N/gildedrose.git'

    }
    stage ('Build'){
        // mvn clean package
        sh 'docker run -i --rm -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn clean package' 
    }
    stage ('Javadoc'){
        sh 'docker run -i --rm -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn site' 
    }
    stage ('Results'){
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts '**/*.jar'
    }
}
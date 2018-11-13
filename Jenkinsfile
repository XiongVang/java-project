properties([pipelineTriggers([githubPush()])])

node('linux') {
    git url: 'https://github.com/XiongVang/java-project.git', branch: 'master'

    stage ('UnitTests') {
        sh 'ant -f test.xml -v'
    }

    stage ('Build') {
        sh 'ant -f build.xml -v'
    }

    stage ('Deploy') {
        sh 'aws s3 cp /workspace/java-pipeline/dist/ s3://vang4999-seis665-assignment9/ --recursive --exclude "*" --include "*.jar"'
    }

    stage ('Report') {
        echo 'Report'
    }
}

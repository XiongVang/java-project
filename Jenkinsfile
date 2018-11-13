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
        echo 'Deploy'
    }

    stage ('Report') {
        echo 'Report'
    }
}

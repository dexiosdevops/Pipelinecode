pipeline {
    agent any
    stages {
        stage("Build Master") {
            when {
               branch 'master'

            }
            steps {
                echo "Building on master"
            }
        }
        stage("Build Dev") {
            when {
               branch 'dev'

            }
            steps {
                echo "Building on 'dev"
                echo "nothing has been changed"
            }
        }
        stage("Build classs") {
            when {
               branch 'classs'

            }
            steps {
                echo "Building on classs"
                echo "Building on classsess"
                echo "nothing is changed"
                echo "something is changed"
                echo "this is from dev-qq"
            }
        }
    }
}

pipeline {
    agent any
    parameters {
        string(name: 'Branch_Name', defaultValue: 'classs', description: 'Mention Branch name here?')
        string(name: 'Git_URL', description: 'Mention URL for Git  here?')
        string(name: 'Commit_ID', description: 'Mention Commit ids here?')
    }
    stages {
        stage ("Checkout external proj") {
            steps {
                git branch: "${params.Branch_Name}",
                credentialsId: 'b6e48ca7-bf5b-453d-bb52-d7bd41a594e9',
                url: "${params.Git_URL}"
                sh "ls -lat"
                sh "git status"
                sh "git branch -a"
                //sh "git add ."
               // sh "git pull"
                sh "git cherry-pick ${params.Commit_ID}"
                withCredentials([usernamePassword(credentialsId: 'b6e48ca7-bf5b-453d-bb52-d7bd41a594e9', usernameVariable: 'Username', passwordVariable: 'Password')]){    
                sh('''
                git config user.name 'viswa1145'
                git config user.email 'viswa1145@gmail.com'
                git config --local credential.helper "!f() { echo username=$Username; echo password=$Password; }; f"
                ''')
                sh 'git push origin "${params.Branch_Name}"'
                    
                }
            }
            
        }
        
    }
}

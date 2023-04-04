pipeline {
    agent any
    def GIT_URL = 'git@github.com:muhzub-vagrant/old_feature_branch_testing.git'
    stages {

        stage('Cleanup Merged Branches') {

            steps {
                sh """
                    git clone $GIT_URL
                    folder=$(basename "$GIT_URL" .git)
                    echo "$folder" 
                    cd "$folder"

                """
            }

            
        }
    }
}

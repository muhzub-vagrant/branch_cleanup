pipeline {
    agent any
    def GIT_URL: 'git@github.com:muhzub-vagrant/old_feature_branch_testing.git'
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

            // steps {
            //     sh """
            //         git branch --merged | grep -v '^*\\|master\\|main\\|develop' | while read branch; do
            //             branch_age=\$(expr \$(date +%s) - \$(git log -1 --pretty=format:'%ct' \$branch))
            //             if [ \$branch_age -gt \$((365 * 2 * 24 * 60 * 60)) ]; then
            //                 echo "Deleting merged branch \${branch} (age: \$((\$branch_age / 86400)) days)"
            //                 git branch -D \${branch}
            //             elif [ \$branch_age -gt \$((60 * 24 * 60 * 60)) ]; then
            //                 echo "Moving merged branch \${branch} to head reference (age: \$((\$branch_age / 86400)) days)"
            //                 git branch -M \${branch} refs/heads/merged/\${branch}
            //             fi
            //         done
            //     """
            // }
            
            // steps {
            //     sh """
            //         git for-each-ref --format='%(refname:short) %(committerdate:unix)' refs/heads/ | while read branch commit_time; do
            //             branch_age=\$(expr \$(date +%s) - \$commit_time)
            //             if [ \$branch_age -gt \$((60 * 24 * 60 * 60)) ]; then
            //                 if ! git merge-base --is-ancestor \${branch} master >/dev/null 2>&1; then
            //                     echo "Deleting unmerged branch \${branch} (age: \$((\$branch_age / 86400)) days)"
            //                     git branch -D \${branch}
            //                 fi
            //             fi
            //         done
            //     """
            // }
        }
    }
}

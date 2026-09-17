pipeline {
    agent {
        label 'machine-2'
    }

    stages {
        stage('git checkout') {
            steps {
                script {
                    try {
                        git branch: params.BRANCH,
                            url: 'https://github.com/Yatishgowdaj/Jenkins_sep.git',
                            credentialsId: params.Cred
                    } catch (Exception e) {
                        echo "Git checkout failed: ${e.getMessage()}"
                        error('Stopping pipeline because Git checkout failed')
                    }
                }
            }
        }

        stage('build') {
            steps {
                echo 'this is stage-2'
            }
        }
    }
}
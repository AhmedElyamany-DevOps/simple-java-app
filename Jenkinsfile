node{
    git branch: 'main', url: 'https://github.com/AhmedElyamany-DevOps/jenkins-project.git'
    stage('build') {
        try
        {
            sh 'echo "build stage"'
        }
        catch (Exception e){
            sh 'echo "exception found"'
            throw e
        }
    
        steps ('build test'){
            sh 'echo "build test stage"'
        }
    }

    stage('test') {
        if (env.BRANCH_NAME == 'feat') {
            sh 'echo "test stage"'    
        }
        else {sh 'echo "skip test stage"'
        }

    }
}
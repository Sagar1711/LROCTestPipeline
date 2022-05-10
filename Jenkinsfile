pipeline {
    parameters {
        string(name: "rc_zip_url", trim: true, description: "Url for release candidate - zip")
        string(name: "rc_tar_url", trim: true, description: "Url for release candidate - tar")
    }
    agent {dockerfile true}
    stages {
        stage('Build Env') {
            steps {
                sh 'ls'
                sh 'gcc --version'
                echo "Here is the parameter: ${params.rc_zip_url}"
                sh "wget -q ${params.rc_zip_url}"
                sh "ls"
                sh "unzip ISIS3-6.0.0.zip"
                sh "cd ISIS3-6.0.0/recipe"
                sh "sh build.sh"
            }
        }
    }
}


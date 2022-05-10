pipeline {
    parameters {
        string(name: "rc_zip_url", trim: true, description: "Url for release candidate - zip")
        string(name: "rc_tar_url", trim: true, description: "Url for release candidate - tar")
    }
    agent {dockerfile true}
    stages {
        stage('Build Env') {
            steps {
                sh 'cat /etc/os-release'
                sh 'gcc --version'
                echo "Here is the parameter: ${params.rc_zip_url}"
                sh "wget -q ${params.rc_zip_url} -O rc.zip"
                sh "ls"
                sh "unzip rc.zip"
                sh "cd ISIS3-6.0.0/recipe"
                sh "sh build.sh"
            }
        }
    }
}


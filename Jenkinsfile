pipeline {
  agent { label 'docker-kitchensink-slave' }
  environment {
    ORG = 'sammuthu1'
    REPO = 'SamsBlog'
    CREDENTIALS_ID = '{{JenkinsCredentialId}}'
    MKDOCS_VERSION = '1.1.2'
    MKDOCS_MATERIAL_VERSION = '7.1.0'
    LC_ALL='en_US.utf-8'
    LANG='en_US.utf-8'
  }
  stages {
    stage('Build & Deploy Docs') {
      when { branch 'master' }
      steps {
        withCredentials([usernamePassword(credentialsId: "$env.CREDENTIALS_ID", usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
          sh """
            . /etc/profile.d/jenkins.sh
            git config --global user.name "${USERNAME}"
            git remote set-url origin https://${USERNAME}:${PASSWORD}@github.optum.com/${env.ORG}/${env.REPO}.git
            export GIT_USER=${USERNAME}:${PASSWORD}
            export GITHUB_HOST=github.optum.com
            mkdocs gh-deploy --force
          """
        }
      }
    }
  }
}

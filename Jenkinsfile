@Library('benji-sl@main') _

pipeline {

    agent any

    tools {
        maven 'maven399'
    }

    stages 
    {

        stage('Build1') 
        {
            steps 
            {
                mavenBuild()
            }
        }
        stage('Build2') 
        {
            steps 
            {
                mavenBuild1.compile()
            }
        }
    }
    post 
    {
        success 
        {
            script 
            {
                emailNotification.successEmail()
            }
        }

        failure 
        {
            script 
            {
                emailNotification.failureEmail()
            }
        }

    }
}


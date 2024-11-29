pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Den1ss/HouseRentingSystemDemo'
            }
        }

        stage('Restore dependencies') {
            steps {
                script {
                    if (isUnix()) {
                        bat 'dotnet restore'
                    }
                    else {
                        bat 'dotnet restore'
                    }
                }
            }
        }

        stage('Start the program') {
            steps {
                script {
                    bat 'start cmd /c "dotnet build"'
                }
            }
        }
        stage('Run tests') {
            steps {
                script {
                    bat 'dotnet test'
                }
            }
        }
    }

    post {
            always {
                echo "CI pipeline completed"
            }
        }
}
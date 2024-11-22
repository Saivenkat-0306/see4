pipeline {
    agent any

    stages {
        stage('Job 1: Clone from GitHub') {
            steps {
                git branch: 'master', url: 'https://github.com/Wilsonbolledula/see4.git'
                echo 'Code cloned successfully!'
            }
        }

        stage('Job 2: Execute Java Program') {
            steps {
                script {
                    def javaFile = 'HelloWorld.java' // Replace with your Java file
                    writeFile file: javaFile, text: '''
                    public class HelloWorld {
                        public static void main(String[] args) {
                            System.out.println("Hello from Java!");
                        }
                    }
                    '''
                    bat 'javac HelloWorld.java'
                    bat 'java HelloWorld'
                }
            }
        }

        stage('Job 3: Execute Python Program') {
            steps {
               script {
                   writeFile file: 'hello.py', text: 'print("Hello from Python!")'
                   bat 'python hello.py'
                      }
                   }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline execution failed!'
        }
    }
}

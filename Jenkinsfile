pipeline {
    agent any

    tools {
        nodejs 'nodejs 20' // 使用 Node.js 工具
    }
    stages {
        stage('Checkout') {
            steps {
                // 从代码仓库中检出前端项目源代码
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // 运行前端项目的构建命令
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                // 导航到构建后的前端项目目录
                sh 'npm install -g http-server'
                sh 'http-server -p 8000'
            }
        }
    }

    // post {
    //     always {
    //         // 清理工作目录或执行其他清理操作
    //         cleanWs()
    //     }
    // }
}


pipeline {
    agent { docker { image 'python:3.10.7-alpine' } }
    stages {
        stage('Scan image') {
            steps {
            // Scan policy is managed in the Compute Console
                prismaCloudScanImage ca: '',
                cert: '',
                dockerAddress: "${env.DOCKER_ADDR}",
                ignoreImageBuildTime: true,
                image: "${env.IMAGE_NAME}:${env.BUILD_NUMBER}",
                key: '',
                logLevel: 'debug',
                podmanPath: '',
                project: '',
                resultsFile: 'prisma_cloud_scan_results.json'
            }
		}	
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
    }
}

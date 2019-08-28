pipeline{
    agent any
    stages {
        stage('Build App'){
            steps{
		echo "Build App now......"
                sh "rm -rf SpringBootHelloWorld"
                sh "git clone https://github.com/hugo01718/SpringBootHelloWorld.git/"
                sh "mvn clean -f SpringBootHelloWorld"
                sh "mvn package -f SpringBootHelloWorld"
		sh "docker build . -t springboot_dockerimage"
		sh "docker login -u hugo01718 -p 213456789"
		//sh "docker push springboot_dockerimage"
            }
        }
        stage('Deploy DEV'){
            steps{
                echo "Deploy DEV now......"
		//oc login -u $username -p $password
		//oc project dev
		//oc new-app springboot_dockerimage
            }
        }
        stage('Promote to UAT'){
            steps{
                input "Deploy to UAT?"
            }
        }
        stage('Deploy UAT'){
            steps{
                echo "Deploy UAT now......"
		//oc login -u $username -p $password
		//oc project qa
		//oc new-app springboot_dockerimage
            }
        }
    }   
}

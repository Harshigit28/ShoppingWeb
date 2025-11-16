# ShoppingWeb

git init
git add .
git commit -m "Initial commit of portfolio website"
git branch -M main
git remote add origin https://github.com/your-username/my-portfolio.git
git push -u origin main


pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Harshigit28/portfolio-repo.git'
            }
        }
        stage('Deploy') {
            steps {
                bat 'xcopy /E /I /Y "%WORKSPACE%\\*" "C:\\inetpub\\wwwroot\\portfolio\\"'
                // Adjust the destination path to your actual deployment folder
            }
        }
    }
}


Using  Docker 
1) Github push
   
2)Dockerfile :
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 

3)docker build -t travel-agency-website:v1 .

4)docker run -d -p 8080:80 travel-agency-website:v1



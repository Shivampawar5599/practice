pipeline {
    agent {
        label {
            label "built-in"
            customWorkspace "/mnt"
        }
    }
    stages {
        stage ("stage-1"){
            steps {
                sh "git clone https://github.com/Shivampawar5599/practice.git -b 23Q1"
                sh "chmod -R 777 /mnt/practice/index.html"
                sh "docker run -d -p 80:80 --name server httpd"
                sh "docker cp /mnt/practice/index.html server:/usr/local/apache2/htdocs"
            }
        }
        stage ("stage-2"){
            steps {
                dir ("/mnt/test") {
                sh "git clone https://github.com/Shivampawar5599/practice.git -b 23Q2"
                sh "chmod -R 777 /mnt/test/practice/index.html"
                sh "docker run -d -p 90:80 --name server-1 httpd"
                sh "docker cp /mnt/test/practice/index.html server-1:/usr/local/apache2/htdocs"
                }
            }
        }
        stage ("stage-3"){
            steps {
                dir ("/mnt/test-1") {
                sh "git clone https://github.com/Shivampawar5599/practice.git -b 23Q3"
                sh "chmod -R 777 /mnt/test-1/practice/index.html"
                sh "docker run -d -p 91:80 --name server-2 httpd"
                sh "docker cp /mnt/test-1/practice/index.html server-2:/usr/local/apache2/htdocs"
                }
            }
        }
    }
}

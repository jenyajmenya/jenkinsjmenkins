pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/jenyajmenya/jenkinsjmenkins.git'

                // Install elk stack.
                sh "apt-get install openjdk-8-jdk"
                sh "apt-get install nginx"
                sh "wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -"
                sh "apt-get install apt-transport-https"
                sh "echo 'deb https://artifacts.elastic.co/packages/7.x/apt stable main' | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list"
                sh "apt-get update"
                sh "apt-get install elasticsearch"
                // Configure Elasticksearch
                sh "cp ./elasticksearch.yml /etc/elasticsearch/elasticsearch.yml"
                sh "systemctl start elasticsearch.service"
                sh "systemctl enable elasticsearch.service"
                sh "apt-get install kibana"
                // Configure Kibana
                sh "cp ./kibana.yml /etc/kibana/kibana.yml"
                sh "systemctl start kibana"
                sh "systemctl enable kibana"
                sh "apt-get install logstash"
                sh "systemctl start logstash"
                sh "systemctl enable logstash"
            }
       }
    }
}

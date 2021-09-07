def git_url = 'https://github.com/rjmsas/prometheus-grafana.git'
def git_branch = 'main'

pipeline
{
    agent
    {
        label 'unode1'
    }

    stages
    {
        stage('env-setup')
        {
            
            steps{
                   sh '''
                   pwd
                   mkdir -p /opt/docker/grafana
                   chmod 777 /opt/docker/grafana/
                   '''
               }
        
        }
        stage('start-dockercompose')
        {
            
            steps{
                   sh '''
                   pwd
                   cd grafana
                   docker-compose -f grafana-compose.yml down | exit 0
                   docker-compose -f grafana-compose.yml up -d
                   '''
               }
        
        }
    }
}

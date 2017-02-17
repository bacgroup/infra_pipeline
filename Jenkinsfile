node{
    stage('Build Infra PostgreSQL Database')
    {
        // Deploy database
        sh 'sudo apt-get -y install postgresql postgresql-contrib'
    }
    stage('Test Infra PostgresSQL Database')
    {
        sh 'mkdir -p test'
        sh '''
        chmod +x port_test.sh
        ./port_test.sh > results.sh
        rm -f results.sh
        '''
        junit 'test/*.xml' // Collect Infra Test Results
    }
}

node {
      stage('init') {
         checkout scm
      }
      stage('build') {
           withCredentials([azureServicePrincipal('demo')]) {
         sh '''
           export AZURE_CLIENT_ID=$AZURE_CLIENT_ID
           export AZURE_CLIENT_SECRET=$AZURE_CLIENT_SECRET
           export AZURE_TENANT_ID=$AZURE_TENANT_ID
           export AZURE_SUBSCRIPTION_ID=$AZURE_SUBSCRIPTION_ID
           python example.py
         '''
       }
   }
}


node
{
  stage('Checkout Source')
  {
    checkout scm
  }

  stage ('Build Image and push to ECR')
  {
    docker.withRegistry('565945558718.dkr.ecr.eu-central-1.amazonaws.com/svehu_aws-deploy-test', 'ecr:eu-central-1:jenkins_aws-access-key_poc')
    {
      docker.build("aws-deploy-test:${env.BRANCH_NAME}", "--pull .").push()
    }
  }

  stage ('Deploy to ECS')
  {
  }
}

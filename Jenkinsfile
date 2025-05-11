pipeline{
  agent any
  parameters{
    choice(name:'VERSION', choices:['1.0.0','1.1.0','1.2.0'], description:'select the version')
    booleanparam(name:'EXECTEST', defaultValue:true, description:'test or no')
  }
  stages{
    stage("init"){
      steps{
        echo "the init stage is running......"
      }
    }
    stage("build"){
      steps{
        echo "the build stage is running......"
      }
    }
    stage("test"){
      when{
        expression{
          params.EXECTEST
        }
      }
      steps{
        echo "the test stage is running......"
      }
    }
    stage("deploy"){
      steps{
        echo "the deploy stage is running......"
        echo "we finished, VERSION ${VERSION} is deployed...."
      }
    }
  }
  post{
    always{
      echo "sending mail to the leader........."
    }
  }
}

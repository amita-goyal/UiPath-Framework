pipeline {
  agent any
  stages {
    stage('Git Pull') {
      steps {
        build 'RunDevelopmentProject'
      }
    }

    stage('UIPath') {
      parallel {
        stage('UIPathWebTests') {
          steps {
            build 'UIPathWebTestOnPremise'
          }
        }

        stage('UIPathAPITests') {
          steps {
            build 'UIPathAPITestOnPremise'
          }
        }

        stage('UIPathMobileTests') {
          steps {
            build 'UIPathBrowserStackMobileTests'
          }
        }

        stage('PerformanceScripts') {
          steps {
            build 'UiPathPerformance'
          }
        }

      }
    }

  }
}
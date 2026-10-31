pipeline{
  agent {label 'docker'}
  stages{
    stage('Build'){
      steps{
        echo 'Building...'
        sh '''#!/bin/bash 
        set -euo pipefail 
        python3 -m py_compile sources/add2vals.py sources/calc.py'''
      }
    }
    stage('Test'){
      steps{
        echo 'Testing'
        sh '''#!/bin/bash
        set -euo pipefail
        python3 -m venv venv && source venv/bin/activate && pip install pytest && pytest sources/test_calc.py  --junitxml=test-reports/results.xml'''
      }
    }
  }
  post{
      always{
        junit 'test-reports/results.xml'
        archiveArtifacts artifacts: 'test-reports/results.xml', allowEmptyArchive: true
      }
  }

}
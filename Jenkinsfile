pipeline{
  agent {label 'docker-1'}
  stages{
    stage('Build'){
      steps{
        echo 'Building...'
        sh '#!/bin/bash \n set -euo pipefail \n python3 -m py_compile sources/add2vals.py sources/calc.py'
      }
    }
  }
}
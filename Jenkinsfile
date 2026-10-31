pipeline{
  agent {docker {image 'python:3.11.4'}}
  stages{
    stage('Build'){
      steps{
        echo 'Building...'
        sh '#!/bin/bash set -euo pipefail; python3 -m py_compile sources/add2vals.py sources/calc.py'
      }
    }
  }
}
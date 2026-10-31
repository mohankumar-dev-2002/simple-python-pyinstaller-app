pipeline{
  stage('Build') {
    agent docker {
      sh '#!/bin/bash set -euo pipefail; python3 -m py_compile sources/add2vals.py sources/calc.py'
    }
  }

}
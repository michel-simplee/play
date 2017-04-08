#! groovy


stage 'Init'
node {
	checkout scm
	sh '''#!/bin/bash
                change_path=$(git diff-tree --no-commit-id --name-only -r HEAD)
                if [[ "$change_path" != "consumer" ]] || [[ "$change_path" != "gems" ]];then
		    echo "Changes: $change_path"
                    echo " NO TEST FOR THIS PATH "
		    exit 1
                fi
	'''
}

stage 'Test'
node {
  parallel (
     phase1: { sh "echo slow; sleep 20s;" },
     phase2: { sh "echo fast; sleep 10s;" }
  )

}


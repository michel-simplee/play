#! groovy


stage 'Init'
node {
	checkout scm
	sh "env"
	/* sh '''#!/bin/bash
                change_path=$(git diff-tree --no-commit-id --name-only -r HEAD)
                echo "$change_path"
                if [[ "$change_path" =~ "consumer" ]] || [[ "$change_path" =~ "gems" ]]
                then
                     echo "MUST BE BUILD"
                     export TEST=1
                else
                    echo " NO PATH TO BUILD"
                fi
	'''*/
}


pipeline{
	agent any

	stages{
		stage("Start selenium grid"){
			steps{
				bat "docker compose -f grid.yaml up -d"
			}
		}
		stage("Run Test suites"){
			steps{
				bat "docker compose -f test-suites.yaml up --pull=always"
			}
		}
	}

	post{
		always{
			bat "docker compose -f grid.yaml down"
			bat "docker compose -f test-suites.yaml down"
		}
	}
}
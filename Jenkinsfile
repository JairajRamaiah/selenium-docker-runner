pipeline{
	agent any

	stages{
		stage("Start selenium grid"){
			bat "docker compose -f grid.yaml up -d"

		}
		stage("Run Test suites"){
			bat "docker compose -f test-suites.yaml up"

		}
	}

	post{
		always{
			bat "docker compose -f grid.yaml down"
			bat "docker compose -f test-suites.yaml down"
		}
	}
}
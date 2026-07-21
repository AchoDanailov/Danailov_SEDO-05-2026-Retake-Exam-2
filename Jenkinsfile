pipeline {
	agent any

	stages {
		stage ("Restore dependencies") {
			when {
				expression {
					return env.BRANCH_NAME == 'main';
				}
			}
			steps {
				sh "dotnet restore"
			}
		}

		stage ("Build") {
			when {
				expression {
					return env.BRANCH_NAME == 'main';
				}
			}
			steps {
				sh "dotnet build --no-restore"
			}
		}

		stage ("Test") {
			when {
				expression {
					return env.BRANCH_NAME == 'main';
				}
			}
			steps {
				sh "dotnet test --no-build --verbosity normal"
			}
		}
	}
}

pipeline {
	agent any

	stages {
		stage ("Restore dependencies") {
			when {
				anyOf {
					branch "main"
				}
			}
			steps {
				sh "dotnet restore"
			}
		}

		stage ("Build") {
			when {
				anyOf {
					branch "main"
				}
			}
			steps {
				sh "dotnet build --no-restore"
			}
		}

		stage ("Test") {
			when {
				anyOf {
					branch "main"
				}
			}
			steps {
				sh "dotnet test --no-build --verbosity normal"
			}
		}
	}
}

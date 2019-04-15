config {
	daysToKeep = 21
	cronTrigger = '@weekend'
}

node() {
	git.checkout { }

	dockerfile.validate { }

	def img = dockerfile.build {
		registry = 'docker-ops.topicusonderwijs.nl'
		name = 'jenkins/jenkins-docker-soapui'
	}
	
	dockerfile.publish {
		image = img
		latestTag = false
		tags = [ "5.5.0" ]
	}
}

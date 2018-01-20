#	microservices-app
#	steps to setup and run inside local dev environment of eclipse IDE 
1.	Import into eclipse as existing maven project choosing the microservices-app-root as project root folder.
2.	Build the microservices-app-root project using "mvn clean install -X -DskipTests".
3.	Run each sub module as spring boot app to create a run configuration of that module in eclipse. Stop the app after it starts.
	This will create the run configuration for that module.
4.	Edit the corresponding run configuration of the module and add into program	arguments "--spring.profiles.active=dev".
	This will activate the dev profile for spring boot project and will detect all the dev spring boot properties from
	application-dev.properties and bootstrap-dev.properties files and give preference to these in dev environment in
	case of ambiguity of properties.
5.	Run sequence of individual modules is
	a,	webservices-registry
	b,	webservices-config-server
	c,	webservices-api-gateway
	then, run any of the service modules
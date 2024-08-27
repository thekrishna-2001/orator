pipeline{
	agent any
	parameters {
  choice choices: ['DEV', 'QA', 'UAT'], name: 'ENVIRONMENT'
}
	triggers {
  pollSCM '* * * * *'
}

	stages{
		stage(checkout){
			steps{
			git 'https://github.com/thekrishna-2001/GRRAS1.git'
			}
		}
		stage(build){
			steps{
				sh 'mvn install'
			}
		}
		stage(deploy){
			steps{
			script{	sh '''if [ $ENVIRONMENT = "QA" ];then
                                        cp target/GRRAS1.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps
                                elif  [ $ENVIRONMENT = "UAT" ];then
                                         cp target/GRRAS1.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps
                                echo "deployment has been done!"
                                fi'''}
	
	}			}
		}
	}

def gv
  pipeline {
	agent any 
     parameters {
	  //string(name:'VERSION',defaultvalue:'',description:'Version to deploy on prod')
	  choice(name:'VERSION',choices:['1.1.0','1.2.0','1.3.0'],description:'')
	  booleanParam(name: 'executeTests',defaultValue:true,description:'')
	}
	stages {
		stage("init") {
		steps {
			script {
				gv = load "script.groovy"
				}
			}
	
			     }
		stage("deploy") {
			expression {
			params.executeTests == true
			}
		steps {
			script {
				gv.buildApp()
				}
			}
			     }
		}	 
	}

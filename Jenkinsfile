node('master') {
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '30')), pipelineTriggers([cron('* * * * * ')])])
    
    stage ('Echo datetime '){
		sh 'date >> /tmp/test.txt' 
	}
    
        
    stage ('Sleep 3'){
	    sh 'sleep 3'
	}
    
        
    stage ('Echo Hello World '){
	    sh 'echo \'Hello World\' >> /tmp/test.txt'
	}
    

    stage ('Finish'){
	    sh 'echo \' ------ \'  >> /tmp/test.txt'
	    slackSend channel: '@quyen.pham', color: 'Red', message: 'Quyền Test Jenkins', teamDomain: 'saleshood', tokenCredentialId: 'Slack'

	}
    
}



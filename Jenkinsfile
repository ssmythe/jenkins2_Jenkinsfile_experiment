def mvn(args) {
    sh "${tool 'Maven 3.3.9'}/bin/mvn ${args}"
}

stage('hello') {
    node {
        echo 'Hello World'
        sh 'date'
        // checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ssmythe/kata_ruby_using_cucumber.git']]])
        sh 'ls -l'
    }
}

stage('maven version') {
    node {
        tool name: 'JDK1.8.0_112', type: 'hudson.model.JDK'
        tool name: 'Maven 3.3.9', type: 'hudson.tasks.Maven$MavenInstallation'
        jdk = tool name: 'JDK1.8.0_112'
        env.JAVA_HOME = "${jdk}"
        sh 'java -version'
        mvn '-version'
    }
}

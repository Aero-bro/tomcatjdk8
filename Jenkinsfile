pipeline{
    agent any
    stages{
        stage("git-clone"){
           steps{
                 script{
                                  out=sh(script:"ls tomcatjdk8",returnStatus:true)
                                  println "--------------"
                                  println out
                                  if(out == 0){
                                    sh "rm -rf feitest"
                                  }
                        }
               sh "git clone https://github.com/Aero-bro/tomcatjdk8.git"
           }
        }
       
        stage("docker-push"){
            steps{
               sh "docker -v"
               sh "docker build -t tomcatjdk8 ."
               sh "docker login --username=慈航普渡aero --password=Zf666888? registry.cn-hangzhou.aliyuncs.com"
               sh "docker tag backend registry.cn-hangzhou.aliyuncs.com/aero_bro/tomcatjdk8:tomcatjdk8"
               sh "docker push registry.cn-hangzhou.aliyuncs.com/aero_bro/tomcatjdk8:tomcatjdk8"
            }
        }
    }
}

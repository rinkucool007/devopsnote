# devopsnote

Tag Strategies :
https://www.jenkins.io/blog/2018/05/16/pipelines-with-git-tags/
https://notesfromthelifeboat.com/post/building-git-tags-with-jenkins/
https://stackoverflow.com/questions/48363217/execute-jenkins-pipeline-step-only-when-building-a-tag



https://github.com/MirandaRompoti/Learning/blob/d649654930e632f0d8f03b4c54ddfd204fa273a1/ForLoops/CI/Jenkins/README.md



https://stackoverflow.com/questions/7911620/using-the-nexus-rest-api-to-get-latest-artifact-version-for-given-groupid-artifa

----------------------------------------------------
# Delete Old Builds :
https://gist.github.com/pkouman/c987ce8cd622820cce9111ea34662c6b
MAX_BUILDS = 10 // max builds to keep

def jobs = Jenkins.instance.items;

for (job in jobs) {
    println "Job: " + job.name
    def recent = job.builds.limit(MAX_BUILDS)
    println "Recent Builds: "  + recent
    println "============================="
    for (build in job.builds) {
        if (!recent.contains(build) && !build.isBuilding()) {
            println "Deleting: " + build
            build.delete()
            println ""
        }
    }
}
--------------------------------------------------------

https://medium.com/@dheerajgambhir/how-to-discard-jenkins-old-builds-from-project-or-pipeline-e2888306a2b6

https://superuser.com/questions/589528/how-do-i-delete-the-builds-11-to-1717-in-jenkins


https://support.cloudbees.com/hc/en-us/articles/215549798-Best-Strategy-for-Disk-Space-Management-Clean-Up-Old-Builds


------------------------------------------------------------------
Jenkins Configuration as Code


https://www.jenkins.io/projects/jcasc/#:~:text=Jenkins%20Configuration%20as%20Code%20provides,in%20a%20fully%20reproducible%20way.

https://github.com/jenkinsci/configuration-as-code-plugin

https://opensource.com/article/20/4/jcasc-jenkins

https://devops.com/using-jenkins-configuration-as-code/

https://www.praqma.com/stories/start-jenkins-config-as-code/

https://medium.com/preply-engineering/jenkins-omg-275e2df5d647


ELK Dashboard :

http://www.tp1rc.edu.tw/tpnet2016/training/10513.pdf?bcsi_scan_efc4f2ce7d38798c=0&bcsi_scan_filename=10513.pdf


sites :

https://www.deploycontainers.com/

https://wilsonmar.github.io/jenkins2-pipeline/

http://grokdebug.herokuapp.com/

https://docs.openstack.org/infra/jenkins-job-builder/

https://codewithharry.com/videos/

https://www.learnitguide.net/

https://8gwifi.org/docs/kube-dash.jsp

https://gradle-ssh-plugin.github.io/docs/


https://mohamicorp.atlassian.net/wiki/spaces/DOC/pages/136740885/Triggering+Jenkins+Based+on+New+Tags


# setup java

JAVA_HOME=/usr/lib/java/jdk1.8.0_221

PATH=$PATH:$HOME/bin:$JAVA_HOME/bin

export JAVA_HOME

export PATH

sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/java/jdk1.8.0_221/bin/javac" 1

sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/java/jdk1.8.0_221/bin/java" 1

sudo update-alternatives --set java /usr/lib/java/jdk1.8.0_221/bin/java

sudo update-alternatives --set javac /usr/lib/java/jdk1.8.0_221/bin/javac

/usr/java/jdk1.8.0_162/bin/javac


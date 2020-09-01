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

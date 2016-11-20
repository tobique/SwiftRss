#!groovy

node ('xcode8'){

  stage 'Stage Checkout'
    checkout()

  stage 'Stage Fastlane Scan'
    test()
}

def checkout() {
    checkout scm
    sh "git submodule init && git submodule update"
}

def test() {
    def branchName = env.BRANCH_NAME
    def appName = "SwiftRss"
    def scheme = "SwiftRss"
    sh "fastlane test branch:'${branchName}' appName:'${appName}' scheme:'${scheme}'"
}

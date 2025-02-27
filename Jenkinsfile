
node {
    checkout scm
    docker.image('node:12').inside() {
        sh 'export ANDROID_HOME="$HOME/Android/Sdk"'
        sh 'export ANDROID_SDK_ROOT="$HOME/Android/Sdk"'
        sh 'export PATH="$ANDROID_HOME/platform-tools:$ANDROID_HOME/emulator:$ANDROID_HOME/cmdline-tools/latest/bin:$PATH"'
        sh 'chmod +x gradlew'
        sh './gradlew clean'
        sh './gradlew app:asembleRelease'
    }

}


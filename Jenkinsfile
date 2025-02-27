pipeline {
    agent any

    environment {
        ANDROID_HOME = "$HOME/Android/Sdk"
        ANDROID_SDK_ROOT = "$HOME/Android/Sdk"
        PATH = "$ANDROID_HOME/platform-tools:$ANDROID_HOME/emulator:$ANDROID_HOME/cmdline-tools/latest/bin:$PATH"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Setup Gradle') {
            steps {
                sh './gradlew clean'
            }
        }

        stage('Build APK') {
            steps {
                sh './gradlew assembleDebug'
            }
        }

        stage('Archive APK') {
            steps {
                archiveArtifacts artifacts: 'app/build/outputs/apk/debug/app-debug.apk', fingerprint: true
            }
        }
    }
}

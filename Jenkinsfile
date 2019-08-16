#!/usr/bin/env groovy
import java.net.URL

node{
    stage('Git Checkout'){
        git 'https://github.com/edureka-git/DevOpsClassCodes.git'
    }
    stage('AB Compile'){
        withMaven(maven:'MyMaven'){
            sh 'mvn compile'
        }
    }
    stage('AB CodeReview'){
        wihMaven(maven:'MyMaven'){
            sh 'mvn pmd:pmd'   
        }
    stage ('Analysis') {
        withMaven(maven:'MyMaven){
            sh '**/target/pmd.xml'
        // publish visuals of target/pmd.xml
         // def mvnHome = tool 'mvn-default'
 
       // sh "$ here we should add the directory where pmd is created pmd:pmd"
        //def pmd = scanForIssues tool: [$class: 'Pmd'], pattern: '**/target/pmd.xml'
        //publishIssues issues:[pmd]

    }
    stage('AB Package'){
        withMaven(maven:'MyMaven'){
            sh 'mvn package'
        }
    }
}

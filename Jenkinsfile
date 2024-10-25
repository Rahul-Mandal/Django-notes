// @Library("Shared") _
// pipeline{
    
//     agent { label "vinod"}
    
//     stages{
        
//         stage("Hello"){
//             steps{
//                 script{
//                     hello()
//                 }
//             }
//         }
//         stage("Code"){
//             steps{
//                script{
//                 clone("https://github.com/LondheShubham153/django-notes-app.git","main")
//                }
                
//             }
//         }
//         stage("Build"){
//             steps{
//                 script{
//                 docker_build("notes-app","latest","trainwithshubham")
//                 }
//             }
//         }
//         stage("Push to DockerHub"){
//             steps{
//                 script{
//                     docker_push("notes-app","latest","trainwithshubham")
//                 }
//             }
//         }
//         stage("Deploy"){
//             steps{
//                 echo "This is deploying the code"
//                 sh "docker compose down && docker compose up -d"
//             }
//         }
//     }
// }


@Library("Shared") _
pipeline {
    agent any

    stages {
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage('Code') {
            steps {
                echo 'Clonning Code'
                script{
                    clone('https://github.com/Rahul-Mandal/Django-notes.git', "main")
                }
             
                echo 'Clone Successfully'
            }
        }
        stage('Build'){
            steps{
                echo 'building image'
             
                script{
                    docker_build("notes-app", "latest", "niren123")
                }
                
                echo 'build successfully'
            }
        }
        stage('Test'){
            steps{
                echo 'This is test'
            }
        }
        stage('Push to Docker Hub'){
            steps{
                echo 'Pushing to docker hub'
                   script{
                       docker_push("notes-app", "latest", "niren123")
                   }
                    }
                    }     
                  
        stage('Deploy'){
            steps{
                echo 'Deploy'
                sh 'docker compose down && docker compose up -d'
            }
        }
    }
}



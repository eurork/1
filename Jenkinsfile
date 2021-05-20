pipeline {
    agent any;
    options {
        copyArtifactPermission('install, deploy');
    }
    stages{
      stage('build') {
        steps {
          sh 'rm -rf archive'
          sh 'echo "rozpoczynam budowanie . . ."'
          sh 'sleep 1'
          sh 'mkdir archive'
          sh 'cd archive'
          sh 'touch plik2.py plik3.rpm plik4.rpm'
          writeFile file: 'plik.sh', text: 'kod w pliku sh. \n 9 \n 8 \n 7 \n 6 \n 5 \n 4\n 3 \n 2 \n 1 \n koniec kodu.'
          sh 'sleep 1'
          sh 'cd ..'
          sh 'echo "koniec budowania."'
          archiveArtifacts artifacts: 'plik.sh', fingerprint: true
          script{
            zip archive: false, dir: 'archive', zipFile: 'test.zip'
            archiveArtifacts artifacts: 'test.zip', fingerprint: true
          }
          sh 'echo "Artefakty zapisane."'
        }
      }
    }
}
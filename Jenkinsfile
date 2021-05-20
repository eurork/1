pipeline {
    agent any;
    options {
        copyArtifactPermission('install, deploy');
    }
    stages{
      stage('build') {
        steps {
          sh 'rm -rf archive'
          sh 'rm plik.sh plik2.py plik3.rpm plik4.rpm'
          sh 'echo "rozpoczynam budowanie . . ."'
          sh 'sleep 1'
          sh 'mkdir archive'
          sh 'touch archive/plik2.py archive/plik3.rpm archive/plik4.rpm'
          writeFile file: 'archive/plik.sh', text: 'kod w pliku sh. \n 9 \n 8 \n 7 \n 6 \n 5 \n 4\n 3 \n 2 \n 1 \n koniec kodu.'
          sh 'sleep 1'
          sh 'echo "koniec budowania."'
          zip archive: false, dir: 'archive', zipFile: 'test.zip'
          archiveArtifacts artifacts: 'test.zip', fingerprint: true
          sh 'echo "Artefakty zapisane."'
        }
      }
    }
}
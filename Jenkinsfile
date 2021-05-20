pipeline {
    agent any;
    environment {
      VERSION = '1.0'
    }
    options {
        copyArtifactPermission("install-${VERSION}, deploy-${VERSION}");
    }
    stages{
      stage('build') {
        steps {
          sh 'rm -rf archive'
          sh 'rm -f plik.sh plik2.py plik3.rpm plik4.rpm test.zip'
          sh 'echo "rozpoczynam budowanie . . ."'
          sh 'sleep 1'
          sh 'mkdir archive'
          sh 'touch archive/plik2.py archive/plik3.rpm archive/plik4.rpm'
          writeFile file: 'archive/plik.sh', text: 'echo "kod w pliku sh." echo "koniec kodu."'
          sh 'sleep 1'
          sh 'echo "koniec budowania."'
          zip archive: false, dir: 'archive', zipFile: 'test.zip'
          archiveArtifacts artifacts: 'test.zip', fingerprint: true
          sh 'echo "Artefakty zapisane."'
        }
      }
    }
}
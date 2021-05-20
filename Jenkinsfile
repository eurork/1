pipeline {
    agent any;
    options {
        copyArtifactPermission('install, deploy');
    }
    stages{
      stage('build') {
        steps {
          sh 'echo "rozpoczynam budowanie . . ."'
          sh 'sleep 1'
          sh 'touch plik2.py plik3.rpm plik4.rpm'
          writeFile file: 'plik.sh', text: 'kod w pliku sh. \n 9 \n 8 \n 7 \n 6 \n 5 \n 4\n 3 \n 2 \n 1 \n koniec kodu.'
          sh 'sleep 1'
          sh 'echo "koniec budowania."'
          zip zipFile: 'test.zip', archive: false, dir: 'archive'
          archiveArtifacts artifacts: 'test.zip', fingerprint: true
          sh 'echo "Artefakty zapisane."'
        }
      }
    }
}

// properties([
//     copyArtifactPermission('install, deploy'),
// ]);
// node {
//     stage('Build') {
//         sh 'cd ..'
//         sh 'echo "rozpoczynam budowanie . . ."'
//         sh 'sleep 1'
//         sh 'touch plik2.py plik3.rpm plik4.rpm'
//         writeFile file: 'plik.sh', text: 'kod w pliku sh. \n 9 \n 8 \n 7 \n 6 \n 5 \n 4\n 3 \n 2 \n 1 \n koniec kodu.'
//         sh 'sleep 1'

//         sh 'echo "koniec budowania."'
//     }
// }

// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//               echo "rozpoczynam budowanie . . ."
//               sleep 1
//               touch plik2.py plik3.rpm plik4.rpm
//               echo "echo 'kod w pliku sh.'" >> plik.sh
//               echo "echo '9 . . .'" >> plik.sh
//               echo "echo '8 . . .'" >> plik.sh
//               echo "echo '7 . . .'" >> plik.sh
//               echo "echo '6 . . .'" >> plik.sh
//               echo "echo '5 . . .'" >> plik.sh
//               echo "echo '4 . . .'" >> plik.sh
//               echo "echo '3 . . .'" >> plik.sh
//               echo "echo '2 . . .'" >> plik.sh
//               echo "echo '1 . . .'" >> plik.sh
//               echo "echo 'koniec kodu'" >> plik.sh
//               sleep 1
//               echo "koniec budowania."
//             }
//         }
//     }
// }
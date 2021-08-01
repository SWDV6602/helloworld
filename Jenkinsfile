#!groovy 

node {
   stage 'Checkout'
        checkout scm

   stage 'Setup'
        sh '/home/ec2-user/.nvm/versions/node/v16.6.0/lib/node_modules/npm/bin/npm-cli.js config set registry  http://registry.npmjs.org/'
        sh 'npm install'

   stage 'Mocha test'
        sh './node_modules/mocha/bin/mocha'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}

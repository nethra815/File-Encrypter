node {
    stage('Build') {
        sh '''
        echo "Building Java project..."
        mkdir -p build
        javac -d build src/*.java
        '''
    }

    stage('Test') {
        sh '''
        echo "Running tests..."
        mkdir -p test-build
        javac -cp build -d test-build test/*.java
        '''
    }

    stage('Deploy') {
        sh '''
        echo "Packaging application..."
        jar cf FileEncrypter.jar -C build .
        '''
    }
}
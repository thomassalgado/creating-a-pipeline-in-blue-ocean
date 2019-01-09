node {
    /*
     * In order to communicate with the MySQL server, this Pipeline explicitly
     * maps the port (`3306`) to a known port on the host machine.
     */
    docker.image('mongo').withRun('--name mongo') { c ->
        /* Wait until mysql service is up */
        /* Run some tests which require MySQL */
        sh 'echo done'
    }
}

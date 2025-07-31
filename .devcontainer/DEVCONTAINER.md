#How to run

1. on your terminal run `xhost +local:docker` as we later want to run the application from the devcontainer (this only works on linux for now)
1. Install and run Gateway from toolbox
1. select devcontainer
1. select new devcontainer
1. select from local project
    1. select intellij as IDE
    1. path to devcotnainer.json is to be selected to this directorys devcontainer.json
1. container build starts and you will see output, if not redo prev step
1. container starts
1. select version 17 as jdk, vendor microsoft openjdk, download
1. check settings in started ide
    1. build,executiondeployment/buildtools/maven/importing 'JDK for importer' should be set to 17
    1. build,executiondeployment/buildtools/maven/runner 'JRE' should be set to 17
    1. build,executiondeployment/buildtools/gradle 'gradle jvm' should be set to 17
    1. build,executiondeployment/compiler/kotlin compiler 'target jvm version' should be set to 17
1. `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh &&  . '/usr/local/cargo/env' &&  export CARGO_HOME=~/.cargo && rustup target add aarch64-unknown-linux-gnu && cargo install cargo-kotars --git https://github.com/JetpackDuba/kotars`
1. also run ` echo 'export JAVA_HOME=/home/dev/.jdks/ms-17.0.15' >> ~/.bashrc && echo 'export PATH=$JAVA_HOME/bin:$PATH' >> ~/.bashrc && source ~/.bashrc` where the path (here `/home/dev/.jdks/ms-17.0.15`) is the path you gave while selecting java 17
1. now sync gradle projects via the elephant icon on the right and then the circled arrows
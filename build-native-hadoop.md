Using Homebrew on OSX:

Install the required dependencies:

brew install protobuf@2.5 gcc autoconf automake libtool cmake snappy gzip bzip2 zlib openssl
Symlink protoc:

ln -s /usr/local/Cellar/protobuf@2.5/2.5.0/bin/protoc /usr/local/bin/protoc
Verify the version (libprotoc 2.5.0):

brew install protobuf250
export PATH="/usr/local/opt/protobuf@2.5/bin:$PATH"

protoc --version
Export build flags:

export OPENSSL_ROOT_DIR="/usr/local/opt/openssl"
export LDFLAGS="-L${OPENSSL_ROOT_DIR}/lib"
export CPPFLAGS="-I${OPENSSL_ROOT_DIR}/include"
export PKG_CONFIG_PATH="${OPENSSL_ROOT_DIR}/lib/pkgconfig"
export OPENSSL_INCLUDE_DIR="${OPENSSL_ROOT_DIR}/include"
Check Hadoop version:

hadoop version
Fetch the Hadoop source for the version returned above and build:

wget https://archive.apache.org/dist/hadoop/core/hadoop-3.1.0/hadoop-3.1.0-src.tar.gz
tar zxvf hadoop-3.1.0-src.tar.gz
cd hadoop-3.1.0-src
mvn package -Dmaven.javadoc.skip=true -Pdist,native -DskipTests -Dtar
Copy the native libs to your Homebrew installation:

cp -R hadoop-dist/target/hadoop-3.1.0/lib/ /usr/local/Cellar/hadoop/3.1.0/lib/
Update hadoop-env.sh:

vi /usr/local/Cellar/hadoop/3.1.0/libexec/etc/hadoop/hadoop-env.sh
Amend HADOOP_OPTS (may be commented out):

export HADOOP_OPTS="-Djava.net.preferIPv4Stack=true -Djava.library.path=/usr/local/Cellar/hadoop/3.1.0/lib/native"
Restart Hadoop and run the following to verify:

hadoop checknative -a
Based on instructions from https://medium.com/@faizanahemad/hadoop-native-libraries-installation-on-mac-osx-d8338a6923db
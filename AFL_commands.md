export CC=/usr/bin/afl-clang-fast
export CXX=/usr/bin/afl-clang-fast++
cmake -DCMAKE_CXX_COMPILER=/usr/bin/afl-clang-fast++ ..

sudo service docker start
sudo chmod 666 /var/run/docker.sock
docker start gramatron_artifact

YAML-CPP 0.6.0
afl-fuzz -i ~/min_testcases/ -o ~/syncdir/ -- ./parse
afl-fuzz -i ~/min_testcases/ -o ~/yaml_cpp_3hours/ -- ./parse
afl-fuzz -i ~/min_testcases/ -o ~/yaml_cpp_over_night/ -- ./parse

cmake -DCMAKE_C_COMPILER=/usr/bin/afl-clang-fast ..
afl-fuzz -i ~/fuzz-input_md4c -o ~/md4c_output_instrumented/ -- ./md2html 
afl-fuzz -i ~/md4c/test/fuzz-input -o ~/md4c_output/ -- ./md2html

afl-fuzz -i ~/fuzz-input_md4c -o ~/json_c_output/ -- ./json_parse

My MD4C VERSION is 0.2.4
$ git clone https://github.com/mity/md4c
$ git checkout 0d1a41a4d25d57e41b19f8c6abbabbf4d40d09ae
$ cd md4c
$ mkdir build
$ cd build
$ cmake -DCMAKE_C_COMPILER=/usr/bin/afl-clang-fast ..
$ make

Fuzz command: -i for input seed path, -o for output result path,  -- for target executable path
my parse executable is at the  ~/yaml-cpp/build/util

$ git clone https://github.com/json-c/json-c.git
$ git checkout json-c-0.11-20130402
$ cd json-c
$ sh autogen.sh
$ export CC=/usr/bin/afl-clang-fast
$ ./configure
$ make
$ sudo make install

afl-fuzz -i ~/cJSON-1.7.14/build/tests/inputs -o ~/cJson_output/ -- ./fuzz_main @@

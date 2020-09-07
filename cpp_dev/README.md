# Contents

1. Google Test - Unit Testing framework
2. CppCheck - Static Code Analyzer

**Note:** More tools will be added.

#Usage

1. Google Test:

i. Navigate to the directory where the unit testing files are present (use circular-buffer present in this Github pofile as an example).

ii. Run the following command from the parent directory of the source.

`$ sudo docker run -v $(pwd):/mnt cpp-dev make run_test`


2. CppCheck:

i. Navigate to the directory where the source is to be analyzed.

ii. Run the following command from the desired directory of the source.

`$ sudo docker run -v $(pwd):/mnt cpp-dev cppcheck ca_demo.cpp` 

3. Clang-Tidy

i. Navigate to the directory where the source is to be analyzed.

ii. Run the following command from the desired directory of the source (this is the simplest case, for more advanced usage see the clang-tidy documentation and append it with the docker command).

`$ sudo docker run -v $(pwd):/mnt clang-tidy -checks='*modernize*' test.cpp -- `



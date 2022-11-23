# CSE15L Lab Report 5

## `grade.sh` code block
```
CPATH=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"
DIRECTORY="student_submissiom"
JUNITTEST="TestListExamples.java"

#check for duplicate directory for cloning
if [[ -d $DIRECTORY ]]; then
    rm -rf $DIRECTORY
fi

git clone $1 $DIRECTORY > /dev/null 2> gitErr.txt
cp $JUNITTEST $DIRECTORY/
cd $DIRECTORY

#check for file
if [[ ! -f ListExamples.java ]]; then
    echo "Missing file: ListExamples.java. Please resubmit."
    exit 2
fi

#compile and run program
javac -cp $CPATH *.java 2> COMPILE_ERR.txt
if [[ $? -ne 0 ]]; then
    echo -e "The program failed to compile!"
    echo -e "Error message:"
    cat COMPILE_ERR.txt
    exit 1
fi

#compiled and run the test
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > TEST_SCORE.txt

errline=`grep "^[\.E]\+$" < TEST_SCORE.txt`
counterr=`grep -o 'E' <<< $errline | wc -l`

echo "$((8-counterr))/8 tests passed."
echo "Junit Report:"
cat TEST_SCORE.txt

```

## Three different student submissions demo
1. All correct methods\
![Image](week9img/1.png)

2. With a syntax error (compiler error)\
![Image](week9img/2.png)

3. Saved in wrong filename\
![Image](week9img/3.png)

## Trace code for demo 1 (All correct methods)

$1-3:
```
CPATH=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"
DIRECTORY="student_submissiom"
JUNITTEST="TestListExamples.java"
```
* just saved as variables in bash, not stdout/stderr, not return codee

$6-7: if block
```
if [[ -d $DIRECTORY ]]; then
    rm -rf $DIRECTORY
fi
```
* the condition will evaluate to true because the submission directory was created in the last submission and still exist in the current directory
* rm -rf $DIRECTORY gives no stdout/err, return code is 0

$18: `javac -cp $CPATH *.java 2> COMPILE_ERR.txt`
* no stdout if succesful, return code 0
* compiler error message will be directed via stderr to COMPILE_ERR.txt file, return code 1

$19-24:
```
if [[ $? -ne 0 ]]; then
    echo -e "The program failed to compile!"
    echo -e "Error message:"
    cat COMPILE_ERR.txt
    exit 1
fi

```
* the condition will evaluate to false because the return code from previous javac command is 0, which means all the file have successfully compiled
* the inner block won't execute

$27: `java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > TEST_SCORE.txt`
* 
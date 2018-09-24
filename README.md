## Python3 continuous integration demo

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python 3.6](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/release/python-360/)
[![Build Status](https://travis-ci.org/rjchallis/test.svg?branch=master)](https://travis-ci.org/rjchallis/test)
[![Coverage Status](https://coveralls.io/repos/github/rjchallis/test/badge.svg?branch=master)](https://coveralls.io/github/rjchallis/test?branch=master)

A template repository to lint and test code using:
* pylint
* pycodestyle
* pydocstyle
* doctest
* pytest
* mock

Configured for continuous integration and coverage checking using:
* Travis CI
* Coveralls

### Running the tests locally

Clone the repository:
```
git clone https://github.com/rjchallis/test.git
```

Install dependencies:
```
cd test
pip install -r requirements.txt
```

Run all tests:
```
./run_tests.sh
```


### Mirroring this repository

To mirror this repository to use as a template for a new project:

```
git clone --bare https://github.com/rjchallis/test.git
```

```
curl -u 'exampleuser' https://api.github.com/user/repos -d '{"name":"new-repository"}'
```

```
cd test.git
git push --mirror https://github.com/exampleuser/new-repository.git
```

```
cd ..
rm -rf test.git
```

```
git clone https://github.com/exampleuser/new-repository.git
cd new-repository
```

Set up pre-commit hook to automate test running:
```
ln -s ../../pre-commit.sh .git/hooks/pre-commit
```

### Setting up continuous integration

* Follow steps 1-3 of the Travis CI ['Getting Started' guide](https://docs.travis-ci.com/user/getting-started/)):

  1. Go to Travis-ci.com and Sign up with GitHub.
  2. Accept the Authorization of Travis CI. You’ll be redirected to GitHub.
  3. Click the green Activate button, and select the repositories you want to use with Travis CI.

* Follow the Travis CI instructions to ['Add your repository to Coveralls'](https://docs.travis-ci.com/user/coveralls/#1-add-your-repository-to-coveralls):

  1. Sign in to Coveralls with your GitHub account.
  2. Click ADD REPOS in the menu.
  3. Click the 'Add your repository to Coveralls' button next to your repository.

* Edit, commit and push to trigger a new build.

* Update the 'Build Status' and 'Coverage Status' badges at the top of this README to point to your repository

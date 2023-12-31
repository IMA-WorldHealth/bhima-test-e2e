# bhima-test-e2e
Setup files for the BHIMA End-to-End test server

## Install the BHIMA test environment
- See [Dev Install Docs](https://docs.bhi.ma/en/for-developers/installing-bhima.html)
- Note: If the installation is on bare metal, either Ubuntu LTS Desktop or Debian will work.
  But if you are running on a container, there may be difficulties with installing snap
  versions of `mysql-server` on Ubuntu, so use Debian instead.

## Set up Docker
- See https://docs.bhi.ma/en/for-developers/installing-bhima.html

## Set up the jenkins user
(Substitute 'jenkins' or your choice of username for <user-account>)
- `sudo adduser <user-account>`
- `sudo usermod -a -G docker <user-account>`
- `sudo usermod -a -G sudo <user-account>`

## Set up the Jenkins test agent files
- CLONE THIS REPOSITORY in the <user-account> account
  - log in as <user-account>
  - `cd /home/<user-account>`
  - `git clone git@github.com:IMA-WorldHealth/bhima-test-e2e.git builds`
  - `ln -s /home/<user-account>/builds/run_tests . `

## Set up BHIMA
- log in as <user-account>
- `cd /home/<user-account>/builds`
- clone the Bhima repo from IMA World Health
   - `git clone https://github.com/IMA-WorldHealth/bhima.git Bhima`

## Set up the jenkins server agent as a docker image
- https://www.jenkins.io/doc/book/using/using-agents/
- https://www.jenkins.io/blog/2022/12/27/run-jenkins-agent-as-a-service/

- RUN THE TESTS
  - `cd <user-account>`
  - Test it: `./run_tests`

## Note:
- Early attempts to run the tests in a Docker container were not succesful.  Those files have been moved to the 'docker' folder.  Files and scripts for Docker containers are in the 'docker' folder.

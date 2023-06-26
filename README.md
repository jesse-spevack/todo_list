# TodoList
I created this todo list application to learn Elixir and Phoenix.

## 🧙‍♂️ Deploy
Deploying this application is a lot of fun. I am using a free-tier EC2 instance with Ubuntu Amazon Machine Image (AMI).

#### SSH onto my ec2
Get the public-ip-address from EC2 Instance details under `Public IPv4 address`. Not the username, in the case below is `ubuntu` because this is an ubuntu AMI. Other AMI's have different username. For Amazon linux, the default username is ec2_user.
```bash
ssh -i ~/.ssh/BabysFirstEC2KeyPair.pem ubuntu@public-ip-address
```

#### Install Erlang:

Update the package manager:
```bash
sudo apt update
```
Install Erlang. Erlang is a dependency for Elixir. This command will install Erlang from the Ubuntu package repositories. 
```bash
sudo apt install erlang -y
```
Verify the Erlang installation. This command will display the installed Erlang version. If the version is displayed without any errors, it indicates that Erlang is installed correctly.
```bash
erl -version
```
Start the Erlang shell:
```bash
erl
```

#### Install Elixir
The command `sudo apt-get install elixir` installs the Elixir programming language on your Ubuntu system. 

Here's what the command does:

1. `sudo`: Runs the command with superuser (root) privileges.
2. `apt-get`: The package management command-line tool for Ubuntu.
3. `install`: Specifies that you want to install a package.
4. `elixir`: The name of the package you want to install.

To confirm that the installation was successful, you can perform the following checks:

1. **Check the Elixir version**:
   Run the following command to check the installed Elixir version:
   ```
   elixir --version
   ```
   If the installation was successful, it should display the version information of Elixir without any errors.

2. **Start the Elixir Interactive Shell (IEx)**:
   Run the following command to start the Elixir Interactive Shell:
   ```
   iex
   ```
   If the shell starts without any errors, it confirms that Elixir is installed and functioning properly.

3. **Execute Elixir code**:
   While in the Elixir Interactive Shell (IEx), you can execute Elixir code to further verify the functionality. For example, you can try executing basic Elixir expressions or using built-in functions to test various features of Elixir.

By performing these checks, you can confirm if the installation of Elixir was successful and ensure that it is working as expected on your Ubuntu system.

To deploy your Phoenix app, here are the remaining steps you can follow:

#### Build your Phoenix app for production
Before deploying, you need to build your Phoenix app for production. Run the following command in the root directory of your Phoenix app:
```bash
MIX_ENV=prod mix phx.digest
```
Run the following command to create a release build of your Phoenix app:

```bash
MIX_ENV=prod mix release
```
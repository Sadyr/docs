## Установка
### Linux

### Предварительные требование
* Иметь доступ в систему с привилегиями sudo 
* Наличие утилиты для разархивации скачанного пакета: unzip или его аналоги
### Установка
1. Скачать установочный файл одним из следующих  способов:
* Использовать команду "curl" . Параметр "-o" указывает название скачанного файла  в системе
```shell
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
```
* Скачать файл перейдя по ссылке в браузере:
URL для скачивание файла:  https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip

2. Разархивировать установочный файл. На этом примере будет использоваться утилита unzip.
```shell
unzip awscliv2.zip
```
3. Запустить установшик
```shell
sudo ./aws/install
```
4. Проверить версию установленной утилиты с помощью следующей команды:
```shell
aws --version
```


## Конфигурирование

```bash
bucket_name="mybucket01"
region=kz-ala-1=""
access_key=""
secret_key=""
endpoint_url="https://mybucket01.object.pscloud.io"

https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html
https://www.cyberciti.biz/faq/how-to-install-aws-cli-on-linux/

```
### Description
* Credentials identify who is calling the API. Access credentials are used to encrypt the request to the AWS servers to confirm your identity and retrieve associated permissions policies. These permissions determine the actions you can perform. For information on setting up your credentials, see Authentication and access credentials.
* Other configuration details to tell the AWS CLI how to process requests, such as the default output format and the default AWS Region.
###  Configuration and credentials precedence
Credentials and configuration settings are located in multiple places, such as the system or user environment variables, local AWS configuration files, or explicitly declared on the command line as a parameter. Certain locations take precedence over others. The AWS CLI credentials and configuration settings take precedence in the following order:
1. Command line options – Overrides settings in any other location, such as the --region, --output, and --profile parameters.
2. Environment variables – You can store values in your system's environment variables.
3. Assume role – Assume the permissions of an IAM role through configuration or the aws sts assume-role command.
4. Assume role with web identity – Assume the permissions of an IAM role using web identity through configuration or the aws sts assume-role command.
5. AWS IAM Identity Center – The IAM Identity Center configuration settings are stored in the config file. Credentials are authenticated when you run the aws configure sso command. The config file is located at ~/.aws/config on Linux or macOS, or at C:\Users\USERNAME\.aws\config on Windows.
6. Credentials file – The credentials and config file are updated when you run the command aws configure. The credentials file is located at ~/.aws/credentials on Linux or macOS, or at C:\Users\USERNAME\.aws\credentials on Windows.






## How to use command line options
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-options.html
```shell
aws s3 ls --profile `profile1`



```


### AWS CLI supported global command line options

In the AWS CLI you can use the following command line options to override the default configuration settings, any corresponding profile setting, or environment variable setting for that single command.

```shell
--debug
--endpoint-url <string>
Specifies the URL to send the request to. For most commands, the AWS CLI automatically determines the URL based on the selected service and the specified AWS Region. 

--output <string>
Specifies the output format to use for this command. You can specify any of the following values:
json – The output is formatted as a JSON string.
yaml – The output is formatted as a YAML string.
yaml-stream – The output is streamed and formatted as a YAML string. Streaming allows for faster handling of large data types.
text – The output is formatted as multiple lines of tab-separated string values. This can be useful to pass the output to a text processor, like grep, sed, or awk.
table – The output is formatted as a table using the characters +|- to form the cell borders. It typically presents the information in a "human-friendly" format that is much easier to read than the others, but not as programmatically useful.

--profile <string>
Specifies the named profile to use for this command. To set up additional named profiles, you can use the aws configure command with the --profile option.

aws configure --profile <profilename>

--region <string>
Specifies which AWS Region to send this command's AWS request to. 






```

### Tools-draft

#### Install 

The AWS Command Line Interface (AWS CLI) is an open source tool that enables you to interact with AWS services using commands in your command-line shell. With minimal configuration, the AWS CLI enables you to start running commands that implement functionality equivalent to that provided by the browser-based AWS Management Console from the command prompt in your terminal program:
#### URLs
https://aws.amazon.com/blogs/developer/aws-cli-v2-is-now-generally-available/

#### New installation mechanisms
AWS CLI v2 provides pre-built binaries for Windows, Linux, and macOS. You no longer need to have Python installed in order to use the AWS CLI. You don’t have to worry about compatible Python versions, virtual environments, or conflicting python packages.

#### AWS configuration mechanisms
AWS CLI v2 introduces several new mechanisms for configuring credentials. We’ve added a new `aws configure import` command to import credentials from the .csv files generated in the AWS Console.
```bash
aws configure import --csv file://path/to/creds.csv

```

#### Draft

#### Через пакетный менеджер dnf 
```bash
https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html

https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-prereqs.html
https://aws.amazon.com/blogs/developer/aws-cli-v2-is-now-generally-available/
https://easycloudsupport.zendesk.com/hc/en-us/articles/360002115372-Installing-the-AWS-Command-Line-Interface


aws cli migration: https://docs.aws.amazon.com/cli/latest/userguide/cliv2-migration-instructions.html

getting started aws cli: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

Configure aws cli: https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html

PATH: https://www.cyberciti.biz/faq/unix-linux-adding-path/

awscli to RockyLinux: https://blog.khmersite.net/p/how-to-install-awscli-on-rockylinux/

aws cli on linux: https://www.cyberciti.biz/faq/how-to-install-aws-cli-on-linux/

enable epel: https://www.cyberciti.biz/faq/how-to-enable-and-install-epel-repo-on-centos-8-x/





// Предварительные требование
* You must be able to extract or "unzip" the downloaded package.
* The AWS CLI uses `glibc`, `groff`, and `less`. These are included by default in most major distributions of Linux.
* - We support the AWS CLI on 64-bit versions of recent distributions of CentOS, Fedora, Ubuntu, Amazon Linux 1, Amazon Linux 2, Amazon Linux 2023, and Linux ARM.
* Because AWS doesnt maintain third-party repositories, we can’t guarantee that they contain the latest version of the AWS CLI.


1. Download the installation file in one of the following ways:
* Use the `curl` command – The `-o` option specifies the file name that the downloaded package is written to. The options on the following example command write the downloaded file to the current directory with the local name `awscliv2.zip`.
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
* Downloading from the URL – To download the installer with your browser, use the following URL: https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip

2. Unzip the installer. If your Linux distribution doesnt have a built in `unzip` command, use an equivalent to unzip it. The following example command unzips the package and creates a directory named `aws` under the current directory.

unzip awscliv2.zip
Note:  When updating from a previous version, the unzip command prompts to overwrite existing files. To skip these prompts, such as with script automation, use the -u update flag for unzip. This flag automatically updates existing files and creates new ones as needed.


// To install the AWS CLI, run the following commands.
sudo ./aws/install

// **To update your current installation** of the AWS CLI, add your existing symlink and installer information to construct the `install` command using the `--bin-dir`, `--install-dir`, and `--update` parameters. The following command block uses an example symlink of `/usr/local/bin` and example installer location of `/usr/local/aws-cli`.

curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
// Unzip package
unzip awscliv2.zip
// To update the AWS CLI, run the following commands.
sudo ./aws/install --bin-dir /usr/local/bin --install-dir /usr/local/aws-cli --update

3. Run the install program. The installation command uses a file named install in the newly unzipped aws directory. By default, the files are all installed to /usr/local/aws-cli, and a symbolic link is created in /usr/local/bin. The command includes sudo to grant write permissions to those directories.
sudo ./aws/install
You can install without `sudo` if you specify directories that you already have write permissions to. Use the following instructions for the `install` command to specify the installation location:
* - Ensure that the paths you provide to the `-i` and `-b` parameters contain no volume name or directory names that contain any space characters or other white space characters. If there is a space, the installation fails.
* `--install-dir` or `-i` – This option specifies the directory to copy all of the files to.
 The default value is `/usr/local/aws-cli`.
 * `--bin-dir` or `-b` – This option specifies that the main `aws` program in the install directory is symbolically linked to the file `aws` in the specified path. You must have write permissions to the specified directory. Creating a symlink to a directory that is already in your path eliminates the need to add the install directory to the user-s `$PATH` variable.
  The default value is `/usr/local/bin`.
./aws/install -i /usr/local/aws-cli -b /usr/local/bin

Note: To update your current installation of the AWS CLI, add your existing symlink and installer information to construct the install command with the --update parameter.
sudo ./aws/install --bin-dir /usr/local/bin --install-dir /usr/local/aws-cli --update

To locate the existing symlink and installation directory, use the following steps:
a. Use the `which` command to find your symlink. This gives you the path to use with the `--bin-dir` parameter.
which aws 
> /usr/local/bin/aws

b. Use the `ls` command to find the directory that your symlink points to. This gives you the path to use with the `--install-dir` parameter.
ls -l /usr/local/bin/aws

4. Confirm the installation with the following command.
aws --version
If the `aws` command cannot be found, you might need to restart your terminal or follow the troubleshooting in
https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-troubleshooting.html




//  Проверяем установлен ли awscli
aws --version
whereis aws

https://blog.khmersite.net/p/installing-aws-cli-on-almalinux/


// Настройка окружения для  Almalinux 9 (подойдет для всех дистрибутивов на базе RHEL 8 и 9 )

dnf repolist
// check  updades for system
sudo dnf check-update
// Begin by upating AlmaLinux to ensure all system packages are current. This step enhances the stability and security of your server:
sudo dnf upgrade  --refresh
// reboot system
sudo reboot
// This command refreshes your package database and upgrade all install pacakges to their latest version
sudo dnf upgrade  --refresh


// Поиск в репозитории пакетов в названии или в коротком описании содержашие слово "aws"
dnf search aws
// // Поиск в репозитории пакетов в названии,  описании  и в URL  содержашие слово "aws"
dnf search all aws
dnf search all aws  | grep -i SDK || CLI
 > awscli.noarch : Universal Command Line Environment for AWS
> python3-boto3.noarch : The AWS SDK for Python
> golang-github-aws-sdk-devel.noarch 

// Простое скачивание пакеты из репозитория для получение полной информации о нем перед скачиванием
sudo dnf download awscli
// Получение информации о пакете
rpm -qi awscli-1.23.10-3.el9.noarch.rpm 
 // Получение списка зависимойтей пакеты
 rpm -qR awscli-1.23.10-3.el9.noarch.rpm 

 
```










#### Обзор инструмента

The AWS Command Line Interface (AWS CLI) is a unified tool to manage your AWS services. With just one tool to download and configure, you can control multiple AWS services from the command line and automate them through scripts.








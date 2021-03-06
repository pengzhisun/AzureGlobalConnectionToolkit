# AzureGlobalConnectionToolkit
The goal of Azure Global Connection Toolkit is to connect different national clouds and to eliminate the friction to migrate applications between the national clouds.

Typically, migration / integration between different Cloud environment has three phases:

1. **Plan**:
During this phase, users are required to investigate the differences between different
cloud environments e.g. Azure Global vs. Azure China/Azure Germany. Differences
in terms of costs and services parity, as well as risks, unfamiliarity and
uncertainty in the new environment, causes the time and efforts required for
migration planning to increase. 

2. **Validate**:
User
also required to validate if their services will be able to run in the targeted
environment. Usually we need to conduct proof of concept or lots of researches
in order to understand the limitations and constraints of the new environment.
The difficulties to get and use a trial account also block users from moving
ahead.

3. **Migrate**:
After
planning and validation have been completed, user needs to investigate how to
migrate/clone their current workloads to the new environment. The complexity of
technologies blocks user from performing a migration in short period of time.

In order to help users in each step, Azure Global Connection Toolkit offers two components:

- **Assessment Tool**:
Assessment
Tool is a quick and simple tool to generate report and to answer FAQ when
migrating Azure Services between different Azure cloud environments.
Information to be provided in the assessment report includes items such as
services parity, cost estimations and important considerations etc. The
assessment tool allows user to perform assessment on
their global Azure subscription to generate plans and validation reports to
assist their migration planning tasks.

- **CICD Tool**:
The
CI/CD (Continuous Integration and Continuous Delivery) Tool is a quick and
simple tool to perform the actual migration For
example, you can leverage the CI/CD tool to migrate your VMs from Azure East
Asia region to Azure China East region. The toolkit will sync your metadata and
configuration between the source and the destination subscriptions, so that
everything will be the same as the original after the migration has been
completed. Moreover, the tool is open source and able to be freely
customized or integrated into your existing DevOps process.

![Connection Toolkit](https://globalconnectioncenter.blob.core.windows.net/githubpics/connectiontoolkit.png)


## Features

### Assessment Tool

* Support the assessment from Global Azure to China Azure or Azure Germany.
* Support the assessment for entire subscription.
* Support the service parity check.
* Support most item for cost estimation.

### CICD Tool

#### PowerShell Version

* Support ARM VM migration only in current release(no classic VM support).
* Support migration between different Azure Cloud Environments e.g. Azure Global to Azure China and Azure Germany.
* Perform pre-migration validation.
* Support rename for resource and DNS.
* Support resize
* PowerShell scripts based and customizable.
* Support metadata and configuration migration (no extension support).

#### Cross Platform NodeJS version

* Support ARM VM migration only in current release(no classic VM support).
* Support migration between different Azure Cloud Environments e.g. Azure Global to Azure China and Azure Germany.
* Perform pre-migration validation.
* NodeJS based and customizable.
* Support metadata and configuration migration (no extension support).

## Supported Environments

### Assessment Tool

* Cloud Environment
  * Microsoft Azure as reference environment 
  * Microsoft Azure in China / Microsoft in Germany as target environment
  
* Client Environment
  * Windows PowerShell 3.0+
  * Internet Connectivity to reference environment and target environment.
  
### CICD Tool

* Cloud Environment
  * Microsoft Azure
  * Microsoft Azure in China
  * Microsoft Azure in Germany

#### PowerShell Version

* Client Environment
  * Windows PowerShell 3.0+
  * Latest Azure PowerShell recommended
  * Internet connectivity to source environment and destination environment

#### Cross Platfrom NodeJS Version

* Client Environment
  * Latest NodeJS
  * Internet connectivity to source environment and destination environment

## Installation

### MSI Installer

1. Download latest [MSI Installer](https://github.com/Azure/AzureGlobalConnectionToolkit/releases/download/0.2.3/AzureGlobalConnectionToolkit.0.2.3.msi) .
2. Run and Install.

You can also find all the previous releases in [Azure Global Connection Toolkit Release](https://github.com/Azure/AzureGlobalConnectionToolkit/releases)

### CICD Cross Platform NodeJS Version

To install CICD cross-platform CLI, run following command to install npm package.

```bash
npm install -g azure-connectiontoolkit-cicd
```

On Linux distributions, you might need to use sudo to successfully run the npm command, as follows:

```bash
sudo npm install -g azure-connectiontoolkit-cicd
```

## Get Started

### Assessment Tool

After installation, run cmdlet in your PowerShell.

```powershell
New-AzureRmMigrationReport -TargetEnvironment AzureChinaCloud 
```

After executing the cmdlet, it will follow the steps to generate report:

1. Ask your credential.
2. Select reference subscription.
3. Generate the report.

### CICD Tool

#### PowerShell Version

After installation, run cmdlet in your PowerShell if you want to perform a migration.

```powershell
Start-AzureRmVMMigration
```

Run cmdlet if you only want to validate.

```powershell
Start-AzureRmVMMigration -JobType Validate
```

#### Cross Platform NodeJS Version

Please visit [CICD Crossplatfrom](https://github.com/Azure/AzureGlobalConnectionToolkit/tree/master/CICD%20Tool/CrossPlatform(NodeJS)) for more details.

After executing the cmdlet, it will follow the steps to perform VM migration:

1. Ask your source credential.
2. Select source subscription.
3. Ask your destination credential.
4. Select destination subscription.
5. Select the VM to migrate.
6. Select the VM destination location.
7. Check the rename information. 
8. Confirm the VM Migration.
9. Start the VM Migration.

If you want to discover more or customize the script, please visit [CICD Tool](https://github.com/Azure/AzureGlobalConnectionToolkit/tree/master/CICD%20Tool)

## More Guidance

If you target to investigate Azure in China, we highly recommend to browse [Azure China Playbook](https://aka.ms/azurechinaplaybook). Azure China Playbook contains the answers of FAQ when users consider to migrate or start using Azure in China.

## Need Help?

Please contact [Azure Global Connection Team](mailto:amcteam@microsoft.com) if you have any issue or feedback.

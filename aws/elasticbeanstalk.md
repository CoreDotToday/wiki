<!-- TITLE: Elasticbeanstalk -->
<!-- SUBTITLE: A quick summary of Elasticbeanstalk -->

# AWS Elasticbeanstalk
## Version Change
`$ aws elasticbeanstalk list-available-solution-stacks`
```
{
    "SolutionStacks": [
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.6 (Passenger Standalone)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.5 (Passenger Standalone)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.4 (Passenger Standalone)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.3 (Passenger Standalone)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.2 (Passenger Standalone)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.1 (Passenger Standalone)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.0 (Passenger Standalone)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 1.9.3",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.6 (Puma)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.5 (Puma)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.4 (Puma)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.3 (Puma)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.2 (Puma)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.1 (Puma)",
        "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.0 (Puma)",
        "64bit Amazon Linux 2018.03 v2.10.0 running Go 1.11.4",
        "64bit Amazon Linux 2018.03 v2.8.0 running Java 8",
        "64bit Amazon Linux 2018.03 v2.8.0 running Java 7",
        "64bit Amazon Linux 2018.03 v3.1.0 running Tomcat 8.5 Java 8",
        "64bit Amazon Linux 2018.03 v3.1.0 running Tomcat 8 Java 8",
        "64bit Amazon Linux 2018.03 v3.1.0 running Tomcat 7 Java 7",
        "64bit Amazon Linux 2018.03 v3.1.0 running Tomcat 7 Java 6",
        "64bit Amazon Linux 2018.03 v2.8.6 running PHP 5.4",
        "64bit Amazon Linux 2018.03 v2.8.6 running PHP 5.5",
        "64bit Amazon Linux 2018.03 v2.8.6 running PHP 5.6",
        "64bit Amazon Linux 2018.03 v2.8.6 running PHP 7.0",
        "64bit Amazon Linux 2018.03 v2.8.6 running PHP 7.1",
        "64bit Amazon Linux 2018.03 v2.8.6 running PHP 7.2",
        "64bit Amazon Linux 2018.03 v2.8.0 running Python 3.6",
        "64bit Amazon Linux 2018.03 v2.8.0 running Python 3.4",
        "64bit Amazon Linux 2018.03 v2.8.0 running Python",
        "64bit Amazon Linux 2018.03 v2.8.0 running Python 2.7",
        "64bit Amazon Linux 2018.03 v2.7.6 running Python 3.6",
        "64bit Amazon Linux 2018.03 v2.7.3 running Python 3.6",
        "64bit Amazon Linux 2018.03 v2.7.1 running Python 3.6",
        "64bit Amazon Linux 2018.03 v2.7.0 running Python 3.6",
        "64bit Amazon Linux 2017.09 v2.6.6 running Python 3.6",
        "64bit Amazon Linux 2017.09 v2.6.5 running Python 3.6",
        "64bit Amazon Linux 2017.09 v2.6.2 running Python 2.7",
        "64bit Amazon Linux 2017.09 v2.6.1 running Python 2.7",
        "64bit Amazon Linux 2017.09 v2.6.0 running Python 3.6",
        "64bit Amazon Linux 2017.09 v2.6.0 running Python 2.7",
        "64bit Amazon Linux 2017.03 v2.5.2 running Python 3.4",
        "64bit Amazon Linux 2017.03 v2.5.2 running Python 2.7",
        "64bit Amazon Linux 2017.03 v2.5.0 running Python 3.4",
        "64bit Amazon Linux 2017.03 v2.4.1 running Python 2.7",
        "64bit Amazon Linux 2017.03 v2.4.0 running Python 2.7",
        "64bit Amazon Linux 2016.09 v2.3.3 running Python 2.7",
        "64bit Amazon Linux 2016.09 v2.3.2 running Python 2.7",
        "64bit Amazon Linux 2016.09 v2.3.1 running Python 2.7",
        "64bit Amazon Linux 2016.09 v2.2.0 running Python 3.4",
        "64bit Amazon Linux 2016.09 v2.2.0 running Python 2.7",
        "64bit Amazon Linux 2016.03 v2.1.6 running Python 2.7",
        "64bit Amazon Linux 2016.03 v2.1.3 running Python 2.7",
        "64bit Amazon Linux 2016.03 v2.1.0 running Python 3.4",
        "64bit Amazon Linux 2016.03 v2.1.0 running Python 2.7",
        "64bit Amazon Linux 2018.03 v4.8.0 running Node.js",
        "64bit Windows Server Core 2016 v1.2.0 running IIS 10.0",
        "64bit Windows Server 2016 v1.2.0 running IIS 10.0",
        "64bit Windows Server Core 2012 R2 v1.2.0 running IIS 8.5",
        "64bit Windows Server 2012 R2 v1.2.0 running IIS 8.5",
        "64bit Windows Server 2012 v1.2.0 running IIS 8",
        "64bit Windows Server 2008 R2 v1.2.0 running IIS 7.5",
        "64bit Windows Server Core 2012 R2 running IIS 8.5",
        "64bit Windows Server 2012 running IIS 8",
        "64bit Windows Server 2012 R2 running IIS 8.5",
        "64bit Windows Server 2008 R2 running IIS 7.5",
        "64bit Amazon Linux 2018.03 v2.12.7 running Docker 18.06.1-ce",
        "64bit Debian jessie v2.12.7 running Go 1.4 (Preconfigured - Docker)",
        "64bit Debian jessie v2.12.7 running Go 1.3 (Preconfigured - Docker)",
        "64bit Debian jessie v2.12.7 running Python 3.4 (Preconfigured - Docker)",
        "64bit Amazon Linux 2018.03 v2.6.6 running Packer 1.0.3",
        "64bit Amazon Linux 2018.03 v2.11.7 running Multi-container Docker 18.06.1-ce (Generic)",
        "64bit Amazon Linux 2018.03 v2.12.7 running GlassFish 5.0 Java 8 (Preconfigured - Docker)"
    ],
    "SolutionStackDetails": [
        {
            "SolutionStackName": "64bit Amazon Linux 2018.03 v2.9.0 running Ruby 2.6 (Passenger Standalone)",
            "PermittedFileTypes": [
                "zip"
            ]
        },
				...
```
`$ aws elasticbeanstalk update-environment --environment-name 'env-name' --solution-stack-name "64bit Amazon Linux 2018.03 v2.8.0 running Python 3.6"`
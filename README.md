# Cloudwatch-agent

## Install Cloud watch agent

> wget https://s3.amazonaws.com/amazoncloudwatch-agent/ubuntu/amd64/latest/amazon-cloudwatch-agent.deb

> sudo dpkg -i amazon-cloudwatch-agent.deb

> sudo systemctl status amazon-cloudwatch-agent.service

Ref Link: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/download-cloudwatch-agent-commandline.html

## Configure Script for collect metrics

> sudo apt-get install unzip
> 
> sudo apt-get install libwww-perl libdatetime-perl

## Install the Monitoring Scripts

> curl https://aws-cloudwatch.s3.amazonaws.com/downloads/CloudWatchMonitoringScripts-1.2.2.zip -O

> unzip CloudWatchMonitoringScripts-1.2.2.zip && \
  rm CloudWatchMonitoringScripts-1.2.2.zip && \
  cd aws-scripts-mon

> ./mon-put-instance-data.pl --mem-util --mem-avail --mem-used --disk-space-util --disk-space-avail --disk-space-used --disk-path=/ --disk-path=/


## Set Cron for the script

> crontab -e
> 2
> */1 * * * * ./mon-put-instance-data.pl --mem-util --mem-avail --mem-used --disk-space-util --disk-space-avail --disk-space-used --disk-path=/ --disk-path=/

save and exit the editor.

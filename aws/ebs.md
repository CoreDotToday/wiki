<!-- TITLE: Ebs -->
<!-- SUBTITLE: A quick summary of Ebs -->

# EBS
## Space
```
sudo growpart /dev/xvda 1
sudo resize2fs /dev/xvda1
```

### 100% usage
```
sudo /sbin/parted ---pretend-input-tty /dev/xvda resizepart 1 yes 100%
```

##### Reference
https://www.elastic.co/blog/autoresize-ebs-root-volume-on-aws-amis
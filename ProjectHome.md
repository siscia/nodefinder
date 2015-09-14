In a dynamic computing environment such as [EC2](http://www.amazon.com/gp/browse.html?node=201590011) it is useful to have Erlang nodes automatically discover each other.  This project contains 3 (+1) strategies for doing so:

  * combonodefinder: detects EC2 hostname and dispatches either to ec2nodefinder or nodefinder as appropriate.
  * nodefinder: multicast UDP based.  a node group corresponds to a multicast ip/port combination.  [multicast is not supported on EC2](http://developer.amazonwebservices.com/connect/thread.jspa?threadID=19554&tstart=0).
  * ec2nodefinder: [ec2-describe-instances](http://docs.amazonwebservices.com/AWSEC2/2007-08-29/DeveloperGuide/CLTRG-describe-instances.html) based.  a node group corresponds to a  [security group](http://docs.amazonwebservices.com/AWSEC2/2007-08-29/DeveloperGuide/distributed-firewall-concepts.html).  only works on [EC2](http://www.amazon.com/gp/browse.html?node=201590011).
  * s3nodefinder: [S3](http://www.amazon.com/gp/browse.html?node=16427261) based. a node group corresponds to an [S3 bucket](http://docs.amazonwebservices.com/AmazonS3/2006-03-01/UsingBucket.html).  works for WAN discovery.

For LAN setups (EC2 and non-EC2), I recommend combonodefinder.

For WAN setups (without multicast routing), s3nodefinder is the only choice.

Another [Dukes of Erl](http://dukesoferl.blogspot.com/) release.
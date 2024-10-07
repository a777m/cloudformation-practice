## Goal Three

This version uses cross stack referencing i.e. imports and exports. The
core idea here is to layer stacks on top of each other. The layers will roughly be:
- vpc
- internet gateway
- route tables
- network access control list
- subnets
- security groups (for EC2s)
- EC2s
- S3

There is a separate connections folder which holds stacks that manage
connections between resources. Tbh that may be overkill but its worth
experimenting with seeing how far is too far RE cross stack referencing.


Notes:
- Order seems to matter in terms of deleting resources

## Goal One

Build Project Omage in one giant yaml file. This does not follow any best
practices, its simply to get things up and running.

Notes on Cloudformation/AWS:
- outputs from one stack can be referenced in another stack (cross template referencing)
- resource names need to be unique within the template
- Maximum of 60 parameters in a single template
- S3 bucket names needs to be globally unique
- subnets can only be associated with one NACL at a time
- Even though a VPC spans all availability zones in a region, each subnet can only be in one zone and cannot span zones.
- Any aws resource that you launch must be in a subnet
- Resources are not always able to communicate with each other across regions
- Difference between NACL and security groups is that NACL stops at the first matching rule (so if deny rule comes after allow, it will never be reached) whereas SGs evaluate all the rules before deciding (if there are both allow and deny rules, they will cancel each other out and not allow traffic)
- Default SG settings are: all inbound traffic is denied, all outbound traffic is allowed
- Different EC2 (virtual) network interfaces (aws name: Elastic Network
Interface) can be associated with different subnets i.e one EC2 can be in
multiple subnets, this needs to be manually configured.

Annoying things about CF:
- Very repetitive - edefining ingress/egress routes, subnets, availability zones etc
- Overly verbose
- Bad errors - not very descriptive and hard to know what caused the error
- “Validate” option in console does nothing beyond syntax errors
- Doing region work is a pain, CF needs to be ran from the region you want (all CF URLs are region based)
- Hard to know what region you are in from CLI but you can use pseudo parameters
to reference region in template (this is also elevated with boto3)

Nice things about CF:
- You can define resources in any order. The CF parser does not go fro top to bottom

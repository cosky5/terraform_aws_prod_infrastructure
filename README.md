# aws_vpc.prod-vpc

## Terraform Command
```terraform init```

To auto run any update made on terraform
```
terraform apply --auto-approve
```

```terraform apply```
Apply any changes made to your resources

```terraform state show aws_eip.two```
# aws_eip.two:
```
resource "aws_eip" "two" {
    associate_with_private_ip = "10.0.1.50"
    association_id            = "eipassoc-0844e1c131fff3220"
    domain                    = "vpc"
    id                        = "eipalloc-0e733bfd40cf0b67b"
    network_interface         = "eni-02153f49f23d1c770"
    private_dns               = "ip-10-0-1-50.ec2.internal"
    private_ip                = "10.0.1.50"
    public_dns                = "ec2-54-160-96-171.compute-1.amazonaws.com"
    public_ip                 = "54.160.96.171"
    public_ipv4_pool          = "amazon"
    vpc                       = true
}
```

```terraform state list```
output
```
aws_eip.two
aws_instance.web-server-instance
aws_internet_gateway.gw
aws_network_interface.web-server-mac
aws_route_table.prod-route-table
aws_route_table_association.a
aws_security_group.allow_web
aws_subnet.subnet_01
aws_vpc.prod-vpc
```

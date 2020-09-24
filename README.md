**Steps:**
1. Create vpc
2. Create Internet Gateway
3. Create custom Roue Table
4. Create a Subnet
5. Associate subnet with Route Table
6. Create a Security Group to allow port 22, 80, 443
7. Create a network interface with an IP in the subnet that was created in step 4
8. Assign an elastic IP to the network interface created in step 7
9. Create an Ubuntu server and install and enable apache2



# aws_vpc.prod-vpc

## Terraform Command
```
$ terraform init
```
The command terraform init will install 
```
* terraform modules
* eventually a backend
* and provider(s) plugins
```

To execute the plan
```
$ terraform apply
```

To auto run any update made on terraform
```
$ terraform apply --auto-approve
```

Apply any changes made to your resources **aws_eip.two**
```
$ terraform state show aws_eip.two
```
```
$ resource "aws_eip" "two" {
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
The list of resources in the 
#### Debug Output

```
$ terraform state list

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

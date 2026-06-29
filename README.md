git clone https://github.com/amolbhadane111-maker/cloudformation---ec2.git
cd cloudformation---ec2

aws cloudformation validate-template \
  --template-body file://template2.yaml

aws cloudformation create-stack \
  --stack-name MyStack \
  --template-body file://template2.yaml

---
Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      AvailabilityZone: us-east-1a
      ImageId: ami-08f44e8eca9095668
      InstanceType: t3.medium

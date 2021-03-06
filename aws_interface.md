# aws interface

```yaml
Metadata:
  AWS::CloudFormation::Interface:
    ParameterGroups:
      - ParameterGroup
    ParameterLabels:
      ParameterLabel
```

AWS::CloudFormation::Interface는 AWS CloudFormation 콘솔에서 파라미터가 그룹화되고 정렬되는 방식을 정의하는 메타데이터 키입니다. <p>
콘솔에서 스택을 생성하거나 업데이트하면 콘솔에는 입력 파라미터가 논리적 ID를 기준으로 사전순으로 나열됩니다. <p>
이 키를 사용하면 사용자가 파라미터 값을 효율적으로 지정할 수 있도록 고유의 파라미터 그룹화 및 정렬을 정의할 수 있습니다. <p>
예를 들어, 모든 EC2 관련 파라미터를 한 그룹으로 그룹화하고 모든 VPC 관련 파라미터를 다른 한 그룹으로 그룹화할 수 있습니다. <p>

파라미터 그룹화 및 정렬 외에도 파라미터의 레이블을 정의할 수 있습니다. <p>
레이블은 파라미터의 논리적 ID 대신 콘솔에 표시되는 표시 이름 또는 설명입니다. <p>
레이블은 사용자가 각 파라미터에 지정할 값을 이해하도록 돕는 데 유용합니다. <p>
예를 들어, KeyPair 파라미터에 Select an EC2 key pair라는 레이블을 지정할 수 있습니다. <p>

reference:
https://docs.aws.amazon.com/ko_kr/AWSCloudFormation/latest/UserGuide/aws-resource-cloudformation-interface.html

example
```yaml
Metadata: 
  AWS::CloudFormation::Interface: 
    ParameterGroups: 
      - 
        Label: 
          default: "Network Configuration"
        Parameters: 
          - VPCID
          - SubnetId
          - SecurityGroupID
      - 
        Label: 
          default: "Amazon EC2 Configuration"
        Parameters: 
          - InstanceType
          - KeyName
    ParameterLabels: 
      VPCID: 
        default: "Which VPC should this be deployed to?"
```

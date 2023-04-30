# rede-CloudFormation
Criando arquitetura de rede via Cloud Formation

Os parâmetros definidos no início do código permitem que o usuário configure o nome da VPC que será criada. Em seguida, é definido um mapeamento para as sub-redes (subnets) que serão criadas dentro da VPC, especificando o CIDR para cada uma delas.

# Seção de recursos (Resources), o template cria os seguintes recursos:

- VPC: uma VPC com o CIDR definido no mapeamento SubnetConfig, nomeada com o nome da VPC fornecido como parâmetro.
- PublicSubnet0: uma subnet pública, com o CIDR definido no mapeamento SubnetConfig, associada à VPC criada anteriormente, e localizada em uma das zonas de disponibilidade definidas no mapeamento AZRegions.
- PrivateSubnet0: uma subnet privada, com o CIDR definido no mapeamento SubnetConfig, associada à VPC criada anteriormente, e localizada em uma das zonas de disponibilidade definidas no mapeamento AZRegions.
- InternetGateway: um gateway de internet para a VPC criada.
- VPCGatewayAttachment: anexa o InternetGateway à VPC criada.
- PublicRouteTable: uma tabela de roteamento pública para a VPC criada.
- PrivateRouteTable: uma tabela de roteamento privada para a VPC criada.
- PublicRoute: uma rota pública que redireciona todo o tráfego de saída para o InternetGateway.
- PublicSubnetRouteTableAssociation: associa a subnet pública à tabela de roteamento pública.

Em resumo, esse código cria uma VPC, com uma subnet pública e uma privada, permitindo que instâncias EC2 lançadas nessas subnets possam se comunicar entre si e com a Internet.

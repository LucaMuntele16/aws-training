# CloudFormation: prima sesiune

## Ce am construit
Un stack cu un security group (SSH de la IP-ul meu, HTTP de oriunde) și o instanță EC2 t3.micro.

## Erori întâlnite
- Tip greșit pentru porturi: le-am scris ca text, iar CloudFormation voia numere. Fix: fără ghilimele.
- Tag-urile trebuie scrise ca perechi `Key` / `Value`, nu ca text simplu.
- `DeletionPolicy: Snapshot` nu e valid pentru security group.
- `SecurityGroups` vs `SecurityGroupIds`: cu subnet se folosește `SecurityGroupIds`, ca listă. Am scris greșit numele proprietății o dată.
- `KeyName` e numele perechii din AWS (nu numele fișierului `.pem`).

## Ce am învățat
- Un template conține doar ce setez. Restul ia valori implicite.
- Citesc eroarea din tab-ul Events: îmi spune exact proprietatea greșită.

## De refăcut
- Parametru pentru IP, output cu IP-ul public, drift detection.
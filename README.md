# Startpaket v46, IaC med CloudFormation

Filerna här är startpunkten för labben i V46. Kopiera dem till mappen `v46` i ditt kursrepo.

- `forsta-template.yaml`, en template med ett enda VPC. Prova hela flödet med den först: validera, deploya, verifiera, riv.
- `parametrar.yaml`, samma VPC med en parameter och en Output. Används för att prova ett change set.
- `natverk.yaml`, skelett för nätverksstacken `novatrix-natverk`. VPC:t, det publika subnätet, en NACL-regel och webbens security group är klara som mönster. Det som står som TODO skriver du själv.
- `data.yaml`, skelett för datastacken `novatrix-data`. Subnet groupen och det genererade lösenordet är klara. Databasen och EFS skriver du själv.
- `webb.yaml`, skelett för webbstacken `novatrix-webb`. Rollen och user data är klara. Själva instansen skriver du själv.

Bygg i ordningen nätverk, data, webb, och riv i omvänd ordning. Validera före varje deploy:

    aws cloudformation validate-template --template-body file://natverk.yaml

Dokumentationen för varje resurstyp finns under "AWS resource and property types reference" hos AWS. Sök på typens namn, till exempel AWS::EC2::Subnet.

Färdiga lösningar ingår inte. Kommentarerna i filerna är på engelska.

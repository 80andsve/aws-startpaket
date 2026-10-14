# Startpaket v47, skalbarhet och tillgänglighet

Lägg filerna i din v47-mapp i kursrepot. Kopiera också `natverk.yaml`, `data.yaml` och `webb.yaml` från din v46-mapp.

- `siteurl.sh` pekar WordPress adress (`siteurl` och `home`) på lastbalanseraren. Körs på `novatrix-web`, efter att lastbalanseraren är Active. Fyll i `ALB_DNS` och `DB_HOST` överst. Databaslösenordet hämtar du i CloudShell med `aws secretsmanager get-secret-value --secret-id <DbSecretArn> --query SecretString --output text`.
- `lasttest.sh` belastar en server i 15 minuter. Kör det på BÅDA gruppens servrar, eftersom gruppen skalar på genomsnittet. Stoppa tidigare med `pkill yes`.
- `skala-startbit.yaml` (VG) är början på skalningsstacken: lastbalanserare, target group och listener. Launch template, Auto Scaling-grupp och skalningspolicy skriver du själv. Kräver att `natverk.yaml` har `novatrix-public-b` och `novatrix-alb-sg` med exporterna `public-b-subnet-id` och `alb-sg-id`. Namnen krockar med det du byggt i konsolen, så riv de resurserna först.

Stegen finns i handledningen Del 17B i Classroom. Inga lösenord, ingen `wp-config.php` och inga nycklar i repot.

# Startpaket v48, monitorering och cloud native

Lägg filerna i din v48-mapp i kursrepot. Kopiera också `natverk.yaml`, `data.yaml` och `webb.yaml` från din v47-mapp. Stegen finns i handledningen Del 20B i Classroom.

- `agent-config.json` är CloudWatch-agentens konfiguration. Klistra in hela innehållet som värde i parametern `AmazonCloudWatch-novatrix` i Parameter Store (Standard, String). Namnet måste börja med `AmazonCloudWatch-`.
- `cwagent-userdata.sh` är user data för en ny version av `novatrix-web-lt`. Den installerar agenten och startar den med konfigurationen från Parameter Store. Gör versionen till default och kör en instance refresh.
- `larm.sh` skapar CPU-larmet för gruppen med ett kommando, testar larmkedjan med `set-alarm-state` och listar alla larm som en tabell.
- `logs-insights.txt` innehåller fyra frågor för Logs Insights. Klistra in en i taget.
- `sajtkoll.py` är Lambda-funktionen `novatrix-sajtkoll` (Python 3.12). Rollens policy och inställningarna står i kommentaren överst. Valfri för G.
- `overvakning-startbit.yaml` (VG) är början på övervakningsstacken: topic, prenumeration och ett larm. Resten skriver du själv. Ange e-postadressen vid deploy, aldrig i filen.

Inga lösenord, ingen e-postadress, ingen `wp-config.php` och inga nycklar i repot.

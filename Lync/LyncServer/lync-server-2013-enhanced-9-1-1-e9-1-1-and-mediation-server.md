---
title: 'Lync Server 2013 : Enhanced 9-1-1 (E9-1-1) et serveur de médiation'
TOCTitle: Enhanced 9-1-1 (E9-1-1) et serveur de médiation
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398903(v=OCS.15)
ms:contentKeyID: 49298918
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enhanced 9-1-1 (E9-1-1) et serveur de médiation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-29_

Les capacités étendues du serveur de médiation lui permettent d’interagir correctement avec les fournisseurs de services Enhanced 9-1-1 (E9-1-1). Aucune configuration spéciale n’est requise sur le serveur de médiation. Par défaut, les extensions SIP requises pour l’interaction E9-1-1 sont incluses dans le protocole SIP du serveur de médiation pour qu’il puisse interagir avec un homologue de passerelle (passerelle RTC, IP-PBX ou contrôleur de frontière de session d’un fournisseur de services de téléphonie Internet, y compris les fournisseurs de services E9-1-1).

La capacité du contrôleur de frontière de session E9-1-1 à interagir avec un pool de serveurs de médiation déterminera si la jonction SIP à un fournisseur de services E9-1-1 peut être raccordée à un pool de serveurs de médiation existant ou nécessitera des serveurs de médiation autonomes. Pour plus d’informations, reportez-vous à [Jonction M:N dans Lync Server 2013](lync-server-2013-m-n-trunk.md)).


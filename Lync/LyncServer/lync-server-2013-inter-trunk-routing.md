---
title: 'Lync Server 2013 : Routage interjonctions'
TOCTitle: Routage interjonctions
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49891616
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routage interjonctions dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-08_

Lync Server 2013 fournit une gestion de session basique grâce à la prise en charge du routage de l’inter jonction. Cette nouvelle capacité permet à Lync Server de fournir des fonctionnalités de contrôle d’appel pour aux systèmes téléphoniques situés en aval. Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (RTC), pour que les appels d’un téléphone PBX (autocommutateur privé)(PBX) puissent être acheminés vers la passerelle RTC et que les appels RTC entrants puissent être acheminés vers un téléphone PBX. De même, Lync Server peut interconnecter au moins deux systèmes IP-PBX pour que des appels puissent être placés et reçus entre les téléphones PBX des différents systèmes IP-PBX.

La figure suivante illustre l’interconnectivité fournie par Lync Server 2013 entre une passerelle RTC et un IP-PBX.

![Diagramme IP-PBX/Passerelle PSTN connectant Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagramme IP-PBX/Passerelle PSTN connectant Lync Server")

La figure suivante illustre la connexion fournie par Lync Server 2013 entre deux systèmes IP-PBX.

![Diagramme IP-PBX/Passerelle PSTN interconnectant Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramme IP-PBX/Passerelle PSTN interconnectant Lync Server")


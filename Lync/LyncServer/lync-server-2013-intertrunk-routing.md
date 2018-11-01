---
title: 'Lync Server 2013 : Routage interjonctions'
TOCTitle: Routage interjonctions
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205272(v=OCS.15)
ms:contentKeyID: 49298952
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Routage interjonctions dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-20_

Lync Server 2013 peut interconnecter un système IP-PBX à une passerelle RTC (réseau téléphonique commuté) afin que les appels émis par un téléphone PBX puissent être acheminés au réseau téléphonique commuté, et que les appels RTC entrants puissent être acheminés à un téléphone PBX (autocommutateur privé). De même, Lync Server 2013 peut interconnecter deux systèmes IP-PBX ou plus afin que les appels puissent être émis et reçus entre des téléphones PBX des différents systèmes IP-PBX.

Cette fonctionnalité de routage d’inter-jonctions peut être configurée à l’aide de l’applet de commande Lync Server Management Shell, **Set-CsTrunkConfiguration**, en utilisant le nouveau paramètre, PstnUsages. Ce paramètre spécifie l’ensemble d’enregistrements d’utilisation RTC à utiliser. Une jonction fait appel à cette utilisation RTC pour déterminer un itinéraire et pour acheminer tous les appels entrants en conséquence.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

Le diagramme suivant présente Lync Server 2013 fournissant une interconnectivité entre une passerelle RTC et un système IP-PBX.

**Routage d’inter-jonctions entre la passerelle et le système IP-PBX**

![Diagramme IP-PBX/Passerelle PSTN connectant Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagramme IP-PBX/Passerelle PSTN connectant Lync Server")

Le diagramme suivant présente Lync Server 2013 interconnectant deux systèmes IP-PBX.

**Routage d’inter-jonctions entre deux systèmes IP-PBXs**

![Diagramme IP-PBX/Passerelle PSTN interconnectant Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramme IP-PBX/Passerelle PSTN interconnectant Lync Server")


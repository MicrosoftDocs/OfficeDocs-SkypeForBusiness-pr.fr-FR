---
title: "Lync Server 2013 : Conf. tech. requise pour la déviation du trafic multimédia"
TOCTitle: Configuration technique requise pour la déviation du trafic multimédia
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398435(v=OCS.15)
ms:contentKeyID: 49297382
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Pour chaque appel vers le réseau téléphonique commuté, le serveur de médiation détermine si les données multimédias provenant du point de terminaison Lync d’origine peuvent être envoyées directement à un homologue du serveur de médiation sans passer par le serveur de médiation. L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) associé à la jonction entre le serveur de médiation où l’appel est routé.

La déviation du trafic multimédia peut être utilisée lorsque les conditions suivantes sont remplies :

  - Un homologue du serveur de médiation doit prendre en charge les fonctionnalités nécessaires à la déviation du trafic multimédia, le plus important étant la capacité à gérer plusieurs réponses dirigées (appelées « boîtes de dialogue préliminaires »). Contactez le fabricant de votre passerelle ou système PBX, ou votre fournisseur ITSP, pour obtenir la valeur du nombre maximal de boîtes de dialogue préliminaires que la passerelle, PBX ou SBC peut accepter.

  - L’homologue du serveur de médiation doit accepter le trafic multimédia directement à partir des points de terminaison Lync. De nombreux fournisseurs ITSP autorisent leur SBC à recevoir du trafic uniquement à partir du serveur de médiation. Contactez votre fournisseur ITSP pour savoir si son SBC accepte le trafic multimédia directement à partir des points de terminaison Lync.

  - Les clients Lync et un homologue du serveur de médiation doivent être correctement connectés, ce qui signifie qu’ils doivent se situer dans la même région réseau ou sur des sites réseau qui se connectent à la région via des liaisons réseau étendu (WAN) qui ne sont soumises à aucune limite de bande passante.

## Voir aussi

#### Concepts

[Modes de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)


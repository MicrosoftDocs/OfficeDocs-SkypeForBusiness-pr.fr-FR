---
title: 'Lync Server 2013 : Prise en charge de plusieurs jonctions'
TOCTitle: Prise en charge de plusieurs jonctions
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205127(v=OCS.15)
ms:contentKeyID: 49298401
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge de plusieurs jonctions dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

La fonctionnalité de Lync Server 2013 prend en charge plusieurs associations entre passerelles et serveurs de médiation. Ces associations sont créées en définissant une jonction, qui est une association logique entre un pool de serveurs de médiation et une passerelle RTC (réseau téléphonique commuté), un contrôleur SBC (Session Border Controller) ou un IP-PBX. Utilisez le Générateur de topologie pour associer des passerelles à des serveurs de médiation (autrement dit des jonctions).

  - Pour associer ou supprimer une jonction dans Lync Server 2013, vous devez d’abord définir une jonction dans le Générateur de topologie. Une jonction se compose de l’association suivante : nom de domaine complet de serveur de médiation, port d’écoute de serveur de médiation, nom de domaine complet de passerelle et port d’écoute de passerelle.

  - Pour configurer plusieurs jonctions, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela apporte une résistance supplémentaire à l’infrastructure Voix Entreprise, ce qui est particulièrement utile dans les scénarios interopérationnels PBX (Private Branch Exchange).

Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer une jonction à un itinéraire, vous devez définir un nom simple pour la jonction dans le Générateur de topologie. Ce nom simple est utilisé comme nom de jonction dans le Panneau de configuration Lync Server, où des jonctions peuvent être associées à des itinéraires. Le nom de jonction simple est utilisé comme nom de passerelle à partir du Lync Server Management Shell.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

L’administrateur doit sélectionner une jonction par défaut associée à un serveur de médiation. Dans le Générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés** . Spécifiez la passerelle par défaut pour le serveur de médiation.

Le schéma suivant illustre les différentes jonctions définies pour chaque serveur de médiation et chaque passerelle.

**Routage de jonction M-N**

![Affectations de plusieurs tronçons.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Affectations de plusieurs tronçons.")


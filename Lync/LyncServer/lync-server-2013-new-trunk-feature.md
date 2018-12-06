---
title: 'Lync Server 2013 : Nouvelle fonctionnalité de jonction'
TOCTitle: Nouvelle fonctionnalité de jonction
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49891461
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nouvelle fonctionnalité de jonction dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Dans Microsoft Lync Server 2013, il est possible de définir plusieurs jonctions entre un serveur de médiation et une passerelle. Microsoft Lync Server 2010 n’autorisait qu’une seule jonction entre un serveur de médiation et une passerelle RTC. Cette fonctionnalité offre la flexibilité nécessaire pour définir des jonctions supplémentaires. Une jonction est une association logique entre, d’une part, un port d’écoute et un nom de domaine complet de serveur de médiation, et d’autre part un port d’écoute et un nom de domaine complet de passerelle RTC. Cette nouvelle fonctionnalité permet de définir très facilement des jonctions à des fins de résistance (où plusieurs serveurs de médiation peuvent être utilisés pour acheminer les appels vers la même passerelle RTC), d’interopérabilité de PBX (où plusieurs jonctions associées à différentes stratégies peuvent être utilisées entre un IP-PBX et un serveur de médiation, et à des fins de configuration de jonctions SIP (où des serveurs de médiation situés dans différents sites ont des jonctions SIP vers l’opérateur référencées par le même nom de domaine complet d’opérateur).

## Voir aussi

#### Concepts

[Nouvelles fonctionnalités Voix Entreprise dans Lync Server 2013](lync-server-2013-new-enterprise-voice-features.md)


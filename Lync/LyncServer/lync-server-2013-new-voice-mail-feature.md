---
title: 'Lync Server 2013 : Nouvelle fonctionnalité de messagerie vocale'
TOCTitle: Nouvelle fonctionnalité de messagerie vocale
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49891424
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nouvelle fonctionnalité de messagerie vocale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-05_

Lync Server 2013 propose désormais une nouvelle fonctionnalité de messagerie vocale appelée « Voice mail Escape ». Cette fonctionnalité peut détecter quand un appel est acheminé vers la messagerie vocale et empêcher l’acheminement immédiat de l’appel vers la messagerie vocale du téléphone mobile de l’utilisateur avant que l’utilisateur puisse répondre. Ce scénario se produit quand l’utilisateur active la sonnerie simultanée sur son téléphone mobile et que ce dernier est éteint, à court de batterie ou hors de portée. Voicemail Escape détecte que la messagerie vocale du téléphone mobile de l’utilisateur a répondu immédiatement à l’appel, et déconnecte l’appel de la messagerie vocale du téléphone mobile. L’appel continue de sonner sur les autres points de terminaison de l’utilisateur, ce qui permet à l’utilisateur de répondre à l’appel. Si l’utilisateur ne répond pas à l’appel, ce dernier est acheminé vers la messagerie vocale d’entreprise.

## Voir aussi

#### Tâches

[Configuration de la redirection vers la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  

#### Concepts

[Nouvelles fonctionnalités Voix Entreprise dans Lync Server 2013](lync-server-2013-new-enterprise-voice-features.md)


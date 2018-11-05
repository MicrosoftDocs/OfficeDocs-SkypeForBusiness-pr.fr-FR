---
title: 'Lync Server 2013 : Création des groupes d’agents Response Group'
TOCTitle: Création des groupes d’agents Response Group
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520969(v=OCS.15)
ms:contentKeyID: 49296696
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création des groupes d’agents Response Group Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-12_

Lorsque vous créez un groupe d’agents, vous sélectionnez les agents affectés au groupe et spécifiez divers autres paramètres du groupe. Vous pouvez ainsi sélectionner la méthode de routage des appels et spécifier si un agent peut se connecter au groupe et s’en déconnecter.

Un agent qui doit se connecter au groupe et s’en déconnecter (différent de la connexion à Lync Server et de la déconnexion de celui-ci) est appelé *agent formel* . Les agents formels doivent être connectés au groupe pour recevoir des appels acheminés vers le groupe. Cela peut être utile pour les agents qui répondent à temps partiel aux appels du groupe. Les agents formels se connectent à leur groupe et s’en déconnectent en cliquant sur un élément de menu dans Lync 2013 pour ouvrir le navigateur Windows Internet Explorer et afficher une console web.

Un agent qui ne doit pas se connecter au groupe ou s’en déconnecter est appelé *agent informel* . Ces agents se connectent automatiquement au groupe lorsqu’ils se connectent à Lync Server. Ils ne peuvent pas se déconnecter du groupe.

> [!NOTE]  
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé en ligne, les appels Response Group sont acheminés vers cet agent.

## Dans cette section

[Création ou modification d’un groupe d’agents dans Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)


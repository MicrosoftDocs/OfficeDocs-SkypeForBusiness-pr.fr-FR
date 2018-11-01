---
title: Migration de la fédération XMPP
TOCTitle: Migration de la fédération XMPP
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49891387
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration de la fédération XMPP

 

_**Dernière rubrique modifiée :** 2012-10-16_

Les versions précédentes d’Office Communications Server fournissaient une passerelle XMPP (Extensible Messaging and Presence Protocol) qu’il était possible de déployer en tant que rôle serveur distinct afin d’autoriser la fédération avec des déploiements XMPP. Dans Lync Server 2013, la fonction XMPP peut être déployée en tant que fonctionnalité. La fonction XMPP est installé dans deux éléments : un proxy XMPP qui s’exécute sur le serveur Edge Lync Server 2013 et la passerelle XMPP qui s’exécute sur le serveur frontal Lync Server 2013.

En ce qui concerne la migration, il est possible de déplacer un compte d’utilisateur Office Communications Server 2007 R2 vers un pool Lync Server 2013 et de continuer à utiliser la passerelle XMPP Office Communications Server 2007 R2. Cela est uniquement possible lorsque le partenaire fédéré XMPP n’est pas configuré dans Lync Server 2013.

En résumé, si Office Communications Server a été déployé avec la passerelle XMPP d’Office Communications Server 2007 R2 et si la fédération XMPP a été activée pour les utilisateurs de l’environnement Office Communications Server 2007 R2 hérité, vous pouvez migrer la fédération XMPP vers Lync Server 2013 en procédant comme suit :

1.  Déployez un pool Lync Server 2013.

2.  Déployez un serveur Edge Lync Server 2013.

3.  Déplacez tous les utilisateurs vers le pool Lync Server 2013.

4.  Créez les certificats et stratégies d’accès XMPP appropriés pour le serveur Edge.

5.  Activez la fédération XMPP dans Lync Server 2013.

6.  Mettez à jour les entrées DNS pour les faire pointer vers la passerelle XMPP de Lync Server 2013.


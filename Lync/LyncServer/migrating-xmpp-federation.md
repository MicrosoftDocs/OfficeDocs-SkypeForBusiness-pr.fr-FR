---
title: Migration de la fédération XMPP
TOCTitle: Migration de la fédération XMPP
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49891508
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration de la fédération XMPP

 

_**Dernière rubrique modifiée :** 2012-10-19_

Les versions précédentes de Lync Server et d’Office Communications Server fournissaient une passerelle XMPP (Extensible Messaging and Presence Protocol) qui pouvait être déployée en tant que rôle serveur distinct pour permettre la fédération avec des déploiements XMPP. Dans Lync Server 2013, la fonctionnalité XMPP peut être déployée en tant que composant fonctionnel. La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge Lync Server 2013 et en tant que passerelle XMPP qui s’exécute sur le serveur frontal Lync Server 2013.

Du point de vue de la migration, un compte d’utilisateur Lync Server peut être déplacé vers un pool Lync Server 2013 et continuer à utiliser la passerelle XMPP héritée. Cela est possible uniquement lorsque le partenaire fédéré XMPP n’est pas configuré dans Lync Server 2013.

En résumé, si Lync Server 2010 a été déployé avec la passerelle XMPP d’Office Communications Server 2007 R2 et si la fédération XMPP a été activée pour les utilisateurs de l’environnement Lync Server 2010 hérité, vous pouvez migrer la fédération XMPP vers Lync Server 2013 en procédant comme suit :

1.  Déployez un pool Lync Server 2013.

2.  Déployez un serveur Edge Lync Server 2013.

3.  Déplacez tous les utilisateurs vers le pool Lync Server 2013.

4.  Créez les certificats et stratégies d’accès XMPP appropriés pour le serveur Edge.

5.  Activez la fédération XMPP dans Lync Server 2013.

6.  Mettez à jour les entrées DNS pour les faire pointer vers la passerelle XMPP de Lync Server 2013.


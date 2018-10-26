---
title: 'Lync Server 2013 : Composants et topologies de la messagerie unifiée locale'
TOCTitle: Composants et topologies de la messagerie unifiée locale
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425711(v=OCS.15)
ms:contentKeyID: 49296523
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants et topologies de la messagerie unifiée locale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-25_

Cette rubrique présente les composants Microsoft Exchange Server 2013 requis pour fournir des fonctionnalités de messagerie unifiée Exchange au déploiement de Lync Server 2013. Elle présente également les topologies prises en charge pour l’intégration de la messagerie unifiée Exchange sur site.

## Composants d’Exchange Server

Pour fournir les fonctionnalités et services de messagerie unifiée Exchange décrits dans [Fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) aux utilisateurs de Voix Entreprise de votre organisation, vous devez déployer un serveur de boîtes aux lettres Microsoft Exchange et serveur d’accès au client, qui héberge les boîtes aux lettres des utilisateurs et fournit un emplacement de stockage pour les messages électroniques et les messages vocaux. La messagerie unifiée Exchange s’exécute en tant que service sur les serveurs de boîtes aux lettres Exchange et les serveurs d’accès au client.

Pour plus d’informations sur les composants de la messagerie unifiée Exchange dans Microsoft Exchange Server 2007 et Microsoft Exchange Server 2010, reportez-vous à [Déploiement de la messagerie unifiée Exchange locale pour fournir la messagerie vocale Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) dans la documentation de déploiement.

## Topologies prises en charge

Vous pouvez déployer Lync Server 2013 et la messagerie unifiée Exchange au sein d’une ou de plusieurs forêts. Si le déploiement couvre plusieurs forêts, vous devez effectuer les étapes d’intégration d’Exchange dans chaque forêt de messagerie unifiée Exchange. Vous devez en plus configurer chaque forêt de Microsoft Exchange pour qu’elle approuve la forêt Lync Server 2013 et la forêt Lync Server 2013 pour qu’elle approuve chaque forêt de messagerie unifiée Exchange. Outre cette approbation de forêts, les paramètres de la messagerie unifiée Exchange de tous les utilisateurs doivent être définis dans les objets Utilisateur de chaque forêt Lync Server 2013.

Lync Server 2013 prend en charge les topologies suivantes pour l’intégration de la messagerie unifiée Exchange :

  - Forêt unique

  - Domaine unique (à savoir, une seule forêt associée à un seul domaine) Lync Server 2013, Microsoft Exchange et les utilisateurs se trouvent tous dans le même domaine.

  - Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants). Lync Server 2013 et les serveurs Microsoft Exchange sont déployés sur des domaines distincts du domaine dans lequel vous créez des utilisateurs. Vous pouvez déployer des serveurs de messagerie unifiée Exchange sur des domaines distincts du pool Lync Server 2013 qu’ils prennent en charge.

  - Plusieurs forêts (à savoir, une forêt de ressources). Lync Server 2013 est déployé sur une seule forêt. Les utilisateurs sont ensuite répartis dans plusieurs forêts. Les attributs de messagerie unifiée Exchange des utilisateurs doivent être répliqués sur la forêt Lync Server 2013.
    
    > [!NOTE]  
    > Il est possible de déployer Exchange sur plusieurs forêts. Chaque organisation Exchange peut fournir une messagerie unifiée Exchange à ses utilisateurs. Les serveurs de messagerie unifiée Exchange peuvent aussi être déployés dans la même forêt que Lync Server 2013.

---
title: "Migr. de LS 2010, conv. de gr. ou conv. de gr. OCS 2007 R2 vers LS 2013, serv. de conv. perm."
TOCtitle: "Migr. de LS 2010, conv. de gr. ou conv. de gr. OCS 2007 R2 vers LS 2013, serv. de conv. perm."
ms:assetid: 5b4d3db1-6eba-4932-b49c-f60bcf9488f9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615442(v=OCS.15)
ms:contentKeyID: 49297331
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente

 

_**Dernière rubrique modifiée :** 2012-10-06_

Les rubriques de cette section vous guident à travers le processus de migration de Lync Server 2010, conversation de groupe ou d’Office Communications Server 2007 R2Group Chat vers le serveur de conversations permanentes de Lync Server 2013. Si vous souhaitez que votre déploiement du serveur de conversations permanentes de Lync Server 2013 coexiste avec un déploiement de Lync Server 2010, conversation de groupe ou d’Office Communications Server 2007 R2Group Chat, ce guide comprend également des informations essentielles pour l’utilisation de cet environnement mixte. Ce guide se concentre principalement sur la migration des données du serveur de conversations permanentes. Pour les utilisateurs qui effectuent une migration à partir des versions héritées de Lync Server vers Lync Server 2013, reportez-vous à [Migration de Lync Server 2010 vers Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) et [Migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

> [!IMPORTANT]  
> Pour cette rubrique, nous partons du principe que vous avez déjà installé Lync Server 2013 en coexistence avec Lync Server 2010 ou Office Communications Server 2007 R2.

> [!IMPORTANT]  
> Ce guide décrit les étapes généralement requises pour accomplir chaque phase de la migration. Il n’aborde pas toutes les topologies de déploiement héritées possibles, ni tous les scénarios de migration possibles. Ainsi, vous n’avez peut-être pas besoin d’effectuer toutes les étapes décrites ou vous devez peut-être en effectuer d’autres, selon votre déploiement. Ce guide propose également des exemples d’étapes de vérification. Ces étapes de vérification sont fournies pour vous aider à comprendre ce que vous devez rechercher afin que chaque phase se déroule correctement au fur et à mesure de la migration. Vous pouvez les modifier en fonction de votre propre processus de migration.

Le présent guide fournit des informations propres à la mise à niveau de votre déploiement existant. Il n’explique pas comment modifier votre topologie existante. Il n’aborde pas l’implémentation des nouvelles fonctionnalités. Lorsqu’une procédure détaillée est expliquée ailleurs, ce guide vous indique le document ou la section de document appropriés.

Ce document définit les termes spécifiés dans la liste suivante.

  - *migration*   
    Déplacement de votre déploiement d’une version antérieure du serveur de conversations permanentes, anciennement appelé serveur Group Chat, vers le serveur de conversations permanentes de Lync Server 2013.

<!-- end list -->

  - *mise à niveau*   
    Installation d’une version plus récente d’un logiciel sur un serveur ou ordinateur client.

<!-- end list -->

  - *coexistence*   
    Environnement temporaire qui existe durant la migration quand certaines fonctionnalités sont déplacées vers le serveur de conversations permanentes de Lync Server 2013 et que d’autres fonctionnalités restent sur une version antérieure du serveur Group Chat.

Le serveur de conversations permanentes est une extension de l’infrastructure de Lync Server 2013. En fonction de votre topologie, vous pouvez effectuer la migration de Lync Server 2010, conversation de groupe ou d’Office Communications Server 2007 R2Group Chat vers le serveur de conversations permanentes de Lync Server 2013. Pour plus d’informations sur les topologies disponibles, sur les exigences techniques et sur la configuration logicielle requise pour la migration du serveur Group Chat, reportez-vous à [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

Si votre organisation nécessite une prise en charge de la conformité, cette fonctionnalité est désormais installée automatiquement avec chaque serveur de conversations permanentes. Il n’est plus nécessaire de disposer d’un serveur distinct pour la conformité.

> [!IMPORTANT]  
> Le serveur de conversations permanentes doit être installé sur un système de fichiers NTFS pour permettre d’appliquer la sécurité du système de fichiers. Le système de fichiers FAT32 n’est pas pris en charge par le serveur de conversations permanentes.<br />
Si votre organisation nécessite une prise en charge de la conformité, cette fonctionnalité est désormais installée automatiquement avec chaque serveur de conversations permanentes. Il n’est plus nécessaire de disposer d’un serveur distinct pour la conformité. Pour plus d’informations sur les modifications du serveur de conversations permanentes de Lync Server 2013, reportez-vous à <a href="lync-server-2013-new-persistent-chat-server-features.md">Nouvelles fonctionnalités du serveur de conversation permanente dans Lync Server 2013</a> dans la documentation de mise en route.

## Dans cette section

  - [Scénario de migration standard - Haut niveau](standard-migration-scenario-high-level.md)

  - [Processus de migration - Détails](migration-process-details.md)

  - [Remarques liées à la coexistence](coexistence-considerations.md)


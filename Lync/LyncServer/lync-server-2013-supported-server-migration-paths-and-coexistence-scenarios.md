---
title: "Lync Server 2013 : Chemins de migr. de serv. et scénarios de coex. pris en ch."
TOCTitle: Chemins de migration de serveurs et scénarios de coexistence pris en charge
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425764(v=OCS.15)
ms:contentKeyID: 49296700
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Chemins de migration de serveurs et scénarios de coexistence pris en charge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-16_

Lync Server 2013 prend en charge la migration à partir de l’un ou l’autre des environnements suivants :

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

La migration à partir d’un environnement exécutant ces deux versions précédentes n’est pas prise en charge. La migration à partir de versions précédentes, telles que Microsoft Office Communications Server 2007 ou Live Communication Server 2005, n’est pas prise en charge. Si votre déploiement précédent incluait Group Chat, vous devez le transférer séparément.

## Méthodes de migration

La migration de toutes les topologies et rôles serveur Lync Server est prise en charge. Vous pouvez effectuer la migration d’une topologie vers une autre, par exemple, du serveur Standard Edition vers le serveur Enterprise Edition.

Lync Server 2013 ne prend en charge que la méthode de migration suivante :

  -   
    **Migration côte à côte.** Dans une migration côte à côte, Lync Server 2013 est déployé parallèlement à un déploiement Microsoft Lync Server 2010 ou Office Communications Server 2007 R2 existant. Vous transférez ensuite les opérations vers les nouveaux serveurs et déplacez les utilisateurs vers Lync Server 2013. Cette méthode requiert des plateformes de serveurs supplémentaires (logiciels et matériel) pendant la migration. Les noms de systèmes et de pools sont différents dans la nouvelle configuration. Si vous devez revenir à la version précédente, vous pouvez retransférer les opérations vers les serveurs précédents.

La migration entre forêts services de domaine Active Directory n’est pas prise en charge.

L’option de migration recommandée est de procéder par phase. Pour plus d’informations sur la migration à partir d’une version précédente, dont sur les phases de déploiement de composants appropriées, reportez-vous aux rubriques suivantes dans la documentation de migration :

  - [Migration de Lync Server 2010 vers Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

## Scénarios de coexistence

Lync Server 2013 peut coexister avec des composants issus d’un déploiement Lync Server 2010 ou Office Communications Server 2007 R2. Le déploiement en parallèle de Lync Server 2013 avec à la fois Lync Server 2010 et Office Communications Server 2007 R2 (déploiement en parallèle des trois versions) n’est pas pris en charge.

Au cours d’une migration par phase dans laquelle un déploiement Lync Server 2010 ou Office Communications Server 2007 R2 coexiste temporairement avec le nouveau déploiement Lync Server 2013, la prise en charge du routage de versions mixtes est limité. Pour plus d’informations, reportez-vous à la documentation de migration.

Vous devez utiliser des ordinateurs séparés et distincts exécutant Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 pour vos instances de base de données Lync Server 2013. Vous ne pouvez pas utiliser la même instance de SQL Server pour un pool de serveurs frontaux Lync Server 2013 et pour un pool de serveurs frontaux Lync Server 2010 ou Office Communications Server 2007 R2. Si vous définissez et configurez Lync Server 2013 dans le Générateur de topologie pour un déploiement qui inclut déjà celui de Lync Server 2010 ou Office Communications Server 2007 R2, le Générateur de topologie ne vous autorisera pas à définir une instance de Lync Server 2013 s’il est déjà utilisé dans la topologie.

Le Générateur de topologie affichera le message suivant pour vous indiquer le problème : « Le serveur SQL \[nom de domaine complet du serveur\] contient déjà une instance SQL hébergeant le rôle « Magasin d’utilisateurs ». »

> [!NOTE]  
> Si vous envisagez de déployer des rôles serveur inédits pour votre déploiement Lync Server 2013, vous devez procéder en premier lieu à la mise à jour de votre déploiement existant comme décrit dans la documentation de migration et la documentation de déploiement, puis déployer les nouveaux rôles serveur comme décrit dans la documentation de planification et la documentation de déploiement. Si vous envisagez la migration d’une version précédente de Group Chat, effectuez-la en dernier, une fois que vous avez transféré tous les autres composants de Lync Server 2010 ou Office Communications Server 2007 R2.

Pour plus d’informations sur la configuration requise pour la coexistence ainsi que sur la coexistence et la migration de Lync Server 2010 ou Office Communications Server 2007 R2 et des composants Lync Server 2013, reportez-vous à [Migration de Lync Server 2010 vers Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) et [Migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) dans la documentation de planification. Pour plus d’informations sur la prise en charge de versions mixtes pour les clients, reportez-vous à [Clients pris en charge provenant d’anciens déploiements dans Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).


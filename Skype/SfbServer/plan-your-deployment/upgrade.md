---
title: Planifier la mise à niveau vers Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Résumé : Découvrez les éléments à prendre en compte lorsque vous planifiez une mise à niveau vers Skype Entreprise Server 2015.'
ms.openlocfilehash: 0b31234bbb0cbc5c2475b241b810430f7595f411
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860595"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planifier la mise à niveau vers Skype Entreprise Server 2015
 
Résumé : Découvrez les éléments à prendre en compte lorsque vous planifiez une mise à niveau vers Skype Entreprise Server 2015.
  
Dans le cadre de votre plan de mise à niveau vers Skype Entreprise Server 2015, utilisez cette rubrique pour comprendre les chemins de mise à niveau recommandés pour Skype Entreprise Server 2015, le fonctionnement de la mise à niveau In-Place, les scénarios de coexistence pris en charge et le processus de mise à niveau.

> [!NOTE]
> Les mises à niveau sur place étaient disponibles en Skype Entreprise Server 2015, mais elles ne sont plus prises en charge dans Skype Entreprise Server 2019. La coexistence côte à côte est prise en charge, consultez [Migration vers Skype Entreprise Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Chemins de mise à niveau recommandés vers Skype Entreprise Server 2015

 Pour effectuer une mise à niveau de Lync Server 2013, Lync Server 2010 ou Office Communications Server 2007 R2 vers Skype Entreprise Server 2015, utilisez les chemins de mise à niveau suivants :
  
> [!CAUTION]
> In-Place La mise à niveau déplace automatiquement les répertoires de conférence de Lync Server 2013 vers Skype Entreprise Server 2015. Toutefois, si vous envisagez de déplacer manuellement des répertoires de conférence, il est très important d’utiliser le Skype Entreprise Server 2015 Management Shell. Si vous essayez d’utiliser Lync Server 2013 Management Shell pour déplacer les répertoires de conférence de Lync Server 2013 vers Skype Entreprise Server 2015, la perte de données peut se produire. En général, chaque fois que vous travaillez avec Skype Entreprise Server 2015 dans n’importe quelle capacité, vous devez utiliser l’ensemble d’outils Skype Entreprise Server 2015.  
  
|**Version**|**Recommandations**|
|:-----|:-----|
|Lync Server 2013  <br/> | Pour effectuer la mise à niveau, utilisez le générateur de topologie Skype Entreprise Server et la nouvelle fonctionnalité de mise à niveau In-Place sur chacun des serveurs associés au pool. consultez [Plan to upgrade from Lync Server 2013 to Skype Entreprise Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and [Upgrade to Skype Entreprise Server 2015](../deploy/upgrade-to-skype-for-business-server.md) for detailed steps. <br/> |
|Lync Server 2010 + Lync Server 2013 (double mode)  <br/> |Tout d’abord, effectuez une mise à niveau vers Lync Server 2013, puis effectuez une mise à niveau vers Skype Entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau In-Place. Toutefois, si votre topologie est Lync Server 2010 principale, vous pouvez également restaurer les composants Lync Server 2013 vers Lync Server 2010, puis effectuer une mise à niveau directement vers Skype Entreprise Server 2015. Dans ce cas, vous ne pourrez pas tirer parti de In-Place Mise à niveau et utiliserez la coexistence directe entre Lync Server 2010 et Skype Entreprise Server 2015. La tri-existence n’est pas prise en charge, mais la coexistence est prise en charge.  <br/> |
|Lync Server 2010  <br/> |Créez un nouveau pool Skype Entreprise Server 2015, puis migrez les utilisateurs vers ce nouveau pool. Vous pouvez ensuite désactiver l’ancien pool Lync Server 2010. La mise à niveau de Lync Server 2010 vers Skype Entreprise Server 2015 est similaire à la mise à niveau de Lync Server 2010 vers Lync Server 2013. Consultez [Migration de Lync Server 2010 vers Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).  <br/> |
|Office Communications Server 2007 R2  <br/> | Choisissez l’une des deux options suivantes : <br/>  Configurez un nouvel environnement Skype Entreprise Server 2015. <br/>  Ou si votre matériel et vos logiciels répondent aux exigences de Skype Entreprise Server 2015, effectuez une mise à niveau vers Lync Server 2013, puis effectuez une mise à niveau vers Skype Entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau In-Place. Pour plus d’informations, consultez [la configuration requise pour Skype Entreprise Server 2015](requirements-for-your-environment/server-requirements.md) et [la migration de Office Communications Server 2007 R2 vers Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013).  <br/> |
   
> [!NOTE]
> SQL Server 2014 est pris en charge dans Skype Entreprise Server 2015, mais n’est pas pris en charge dans Lync Server 2013. Si vous souhaitez effectuer une mise à niveau de SQL Server 2012 vers SQL Server 2014, le pool doit d’abord être mis à niveau vers Skype Entreprise Server 2015 à l’aide de la méthode de mise à niveau In-Place, comme décrit dans ce document. Vous pouvez ensuite effectuer une mise à niveau de SQL Server 2012 vers SQL Server 2014, voir [Mise à niveau vers SQL Server 2014](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014). Pour en savoir plus sur les exigences de base de données, consultez [Les exigences de serveur pour Skype Entreprise Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planifier la mise à niveau de Lync Server 2013 vers Skype Entreprise Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Vous pouvez mettre à niveau les systèmes Lync Server 2013 vers Skype Entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau In-Place. La mise à niveau sur place fournit une solution en un clic qui sauvegarde les certificats, désinstalle les composants serveur, met à niveau les bases de données locales et installe les rôles Skype Entreprise Server 2015. La mise à niveau sur place vise à préserver les investissements existants en matériel et serveur, ce qui réduit le coût global de déploiement Skype Entreprise Server 2015.
  
> [!NOTE]
> In-Place La mise à niveau vous permet d’utiliser le même matériel lors de la mise à niveau vers Skype Entreprise Server. Toutefois, la réutilisation du même matériel ne se traduit pas par la même capacité de performances. Vous ne devez pas vous attendre à ce que les charges de performances pour Lync Server 2013 et Skype Entreprise Server 2015 soient identiques. 
  
> [!NOTE]
> In-Place mise à niveau ne prend pas en charge la haute disponibilité ou la récupération d’urgence pour Skype Entreprise Server. 
  
La mise à niveau sur place implique de mettre le pool Lync Server 2013 hors connexion et de le mettre à niveau vers un pool Skype Entreprise Server 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Créer un plan de mise à niveau In-Place

Effectuez un plan qui inclut :
  
1. Compréhension de votre topologie actuelle.
    
    > [!NOTE]
    > Veillez à désinstaller l’outil de Administration LRS pour Lync Server 2013 avant d’exécuter In-Place mise à niveau. L’outil de Administration LRS pour Lync Server 2013 ne peut pas coexister avec Skype Entreprise Server 2015. Après avoir exécuté In-Place mettre à niveau, installez le nouvel outil de Administration LRS. Pour plus d’informations, consultez [le portail web d’administration du système de salle Microsoft Lync pour Skype Entreprise Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807).
  
2. Pool principal pour la mise à niveau.
    
3. Que vous mettiez à niveau les bases de données d’archivage et de surveillance ou que vous en créiez de nouvelles.
    
4. La méthode de mise à niveau In-Place que vous utiliserez : Hors connexion ou Déplacer des utilisateurs. Dans le cadre de Déplacer des utilisateurs, vous devez également migrer les répertoires de conférence globaux associés au pool principal. 
    
5. Un plan de communication pour les utilisateurs concernés.
    
6. Plan de sauvegarde en cas d’échec des mises à niveau.
    
Tous les utilisateurs qui se trouvent dans le pool principal pendant sa mise à niveau ne pourront pas utiliser les services tant que la mise à niveau n’est pas terminée. Si vous disposez d’un pool secondaire opérationnel, vous pouvez éviter d’affecter les utilisateurs en les déplaçant vers le pool secondaire avant la mise à niveau. Après la mise à niveau, déplacez les utilisateurs vers le pool principal.
  
### <a name="in-place-upgrade-methods"></a>Méthodes de mise à niveau sur place

Il existe deux scénarios de mise à niveau In-Place : 
  
- Méthode Move User, qui ne nécessite aucun temps d’arrêt pour les utilisateurs. 
    
- Méthode hors connexion, qui nécessite des temps d’arrêt.
    
Nous recommandons qu’une mise à niveau de méthode hors connexion soit planifiée pendant une fenêtre de maintenance et que les utilisateurs soient informés du temps d’arrêt.
  
> [!NOTE]
> Lors de la mise à niveau d’un pool appairé sur Lync Server 2013 et que vous souhaitez mettre à niveau les deux pools vers Skype Entreprise Server 2015. Veillez à mettre à niveau le deuxième pool immédiatement après la mise à niveau du premier pool. Quand un pool exécute Lync Server 2013 et que le deuxième pool s’exécute Skype Entreprise Server 2015, les options de récupération d’urgence sont réduites. Par exemple, si un pool exécute 2013 et que le second est 2015 et qu’il y a une catastrophe, vous pouvez subir une perte de données, car le basculement de pool n’est pas pris en charge en mode catastrophe lorsque les pools jumelés ne sont pas la même version. 
  
#### <a name="in-place-upgrade-offline-method"></a>Méthode hors connexion de mise à niveau sur place

Utilisez cette méthode si vous ne souhaitez pas déplacer d’utilisateurs entre des pools d’utilisateurs. Pendant la mise à niveau, les utilisateurs ne pourront pas utiliser les services Lync ou Skype Entreprise. 
  
Le diagramme suivant montre une vue d’ensemble de ce processus.
  
![Lync 2013 Pour Skype utilisateurs hors connexion.](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Si vous avez des pools appairés, ne les supprimez pas avant la mise à niveau. 
  
Une fois que vous avez commencé à mettre à niveau un pool de serveurs, vous devez effectuer la mise à niveau de l’ensemble du pool. Skype Entreprise Server ne prend pas en charge la mise à niveau d’une partie seulement du pool. 
  
#### <a name="move-users-method-no-user-downtime"></a>Méthode Move Users (aucun temps d’arrêt de l’utilisateur)
<a name="bkmk_MoveUsersMethod"> </a>

Pour utiliser cette méthode, vous déplacez les utilisateurs vers un autre pool avant de commencer la mise à niveau. Pendant la mise à niveau, les utilisateurs peuvent utiliser les services Lync. Une fois déplacés vers le pool mis à niveau, ils peuvent utiliser Skype Entreprise. Le diagramme suivant montre une vue d’ensemble de ce processus.
  
> [!IMPORTANT]
> Dans le cadre de Déplacer des utilisateurs, vous devez également migrer les répertoires de conférence globaux associés au pool principal. La conférence rendez-vous RTC résout toujours ConferenceID en pool mis à niveau, au lieu du pool appairé. Vous devez donc déplacer les répertoires de conférence, si vous souhaitez que les conférences RTC planifiées dans le pool soient accessibles pendant la mise à niveau. 
  
![Diagramme de natation montrant les utilisateurs déplacés vers un autre pool avant la mise à niveau du pool et déplacés vers le pool après sa mise à niveau.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Déplacer des utilisateurs pour la mise à niveau matérielle
<a name="bkmk_MoveUsersMethod"> </a>

 Si votre matériel ne répond pas aux [exigences du serveur pour Skype Entreprise Server 2015](requirements-for-your-environment/server-requirements.md), configurez un nouvel environnement Skype Entreprise Server 2015 et déplacez les utilisateurs vers cet emplacement. Le diagramme suivant montre une vue d’ensemble de ce processus de mise à niveau à partir de Lync Server 2010. 
  
![Diagramme de couloir de nage montrant les utilisateurs du pool frontal principal Lync Server déplacé vers Skype Entreprise Server 2015 et le pool Lync Server en cours de désaffectation.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Processus de mise à niveau sur place

 Effectuez une mise à niveau de Lync Server 2013 vers Skype Entreprise Server 2015 en procédant comme suit :
  
1. Sauvegardez toutes les bases de données avant la mise à niveau.
    
2. Assurez-vous que tous les services à mettre à niveau sont en cours d’exécution.
    
3. Mettez à niveau et publiez le fichier de topologie à l’aide du générateur de topologie.
    
4. Arrêtez tous les services sur tous les serveurs frontaux.
    
5. Installez les nouvelles conditions préalables requises pour Skype Entreprise Server.
    
6. Sur chaque serveur frontal, démarrez la mise à niveau In-Place.
    
7. Une fois la mise à niveau terminée, redémarrez tous les services.
    
   - Pour le pool frontal, redémarrez les services à l’aide de la commande Start-CsPool.
    
   - Pour les serveurs non frontaux, utilisez Start-CSWindowsService.
    
> [!NOTE]
>  Si vous ne souhaitez pas mettre à niveau vos bases de données d’archivage et de surveillance existantes, supprimez la dépendance avant de mettre à niveau la topologie. Si vous souhaitez créer des bases de données d’archivage et de surveillance, pendant la mise à niveau, vous pouvez créer un magasin SQL et l’associer au pool. Vous trouverez les étapes à suivre dans la rubrique [Mise à niveau vers Skype Entreprise Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > mise à niveau sur place ne prend pas en charge la haute disponibilité ou la récupération d’urgence pour Skype Entreprise Server. Pour éviter d’interrompre les services des utilisateurs, utilisez la [méthode Move Users (aucun temps d’arrêt de l’utilisateur)](upgrade.md#bkmk_MoveUsersMethod) pour mettre à niveau.> Pendant le processus de mise à niveau, le réplica xds est placé dans le dossier partagé local sur le lecteur de disque avec l’espace le plus libre. Si ce disque est supprimé ultérieurement, vous pouvez rencontrez des problèmes tels que le fait que les services ne démarrent pas.
  
### <a name="upgrade-order"></a>Ordre de mise à niveau

Mettez à niveau la topologie de l’intérieur vers l’extérieur. Mettez d’abord à niveau tous vos pools, puis les serveurs de périphérie, puis le pool CMS (Central Management Store). 
  
### <a name="kerberos-authentication-considerations"></a>Considérations relatives à l’authentification Kerberos

Si vous utilisez l’authentification Kerberos pour les services web, vous devez réaffecter des comptes Kerberos et réinitialiser le mot de passe une fois la mise à niveau In-Place terminée. Pour savoir comment procéder, consultez Configuration de [l’authentification Kerberos](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Prise en charge de la coexistence avec Lync Server 2013 et Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Vous pouvez exécuter Skype Entreprise Server 2015 dans la même topologie que Lync Server 2013 ou Lync Server 2010, mais vous ne pouvez pas avoir les trois dans la même topologie.
  
Si vous avez une coexistence entre Lync Server 2010 et Lync Server 2013, il est recommandé de mettre à niveau l’intégralité de la topologie vers Lync Server 2013, puis de passer à Skype Entreprise Server 2015 à l’aide de la mise à niveau In-Place. Pour plus d’informations, consultez [Migration de Lync Server 2010 vers Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).
  
Si votre topologie est principalement Lync Server 2010, restylez les composants Lync Server 2013 vers Lync Server 2010 avant de mettre à niveau la topologie vers Skype Entreprise Server 2015. Dans ce cas, vous perdez l’avantage de la mise à niveau In-Place et disposez d’une topologie de coexistence entre Lync Server 2010 et Skype Entreprise Server 2015.
  
Le diagramme suivant illustre la prise en charge de la coexistence de Skype Entreprise Server 2015 avec Lync Server 2013 et Lync Server 2010.
  
![Diagramme montrant la prise en charge de la coexistence pour Skype Entreprise Server 2015 avec Lync Server 2013 ou Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Processus de mise à niveau avec survivable Branch Appliance et server existants
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype Entreprise Server 2015 ne prend pas en charge une mise à niveau In-Place d’un survivable Branch Appliance (SBA) ou d’un serveur survivable Branch Server (SBS).
  
Toutefois, nous prenons en charge la coexistence de Skype Entreprise Server centres de données avec Lync Server 2010 ou Lync Server 2013 SBA/SBS. 
  
Lors de la planification d’une mise à niveau In-Place d’un pool frontal Lync Server 2013 avec une branche associée, vous pouvez laisser les utilisateurs existants sur Lync Server 2013 SBA/SBS. Pendant la mise à niveau, les utilisateurs SBA/SBS passent en mode résilience et reviennent à la fonctionnalité normale une fois la mise à niveau terminée. Pour plus d’informations sur l’expérience des utilisateurs pendant le mode de résilience, consultez [les fonctionnalités de résilience de site de branche dans Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features).
  
Lors de la migration d’une topologie Lync Server 2010 vers Skype Entreprise Server 2015, le SBA/SBS doit être ajouté à la topologie, à l’instar de la migration vers Lync Server 2013. Pour connaître les étapes requises, consultez [Connecter Survivable Branch Appliance au pool frontal Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool).
  
Pour les topologies de coexistence de Lync Server 2010 et Lync Server 2013, alignez-vous d’abord sur les recommandations de la section « Prise en charge de la coexistence avec Lync Server 2013 et Lync Server 2010 ».
  
## <a name="see-also"></a>Voir aussi
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Mise à niveau vers Skype Entreprise Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Exigences environnementales pour Skype Entreprise Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Configuration requise pour Skype Entreprise Server 2015](requirements-for-your-environment/server-requirements.md)

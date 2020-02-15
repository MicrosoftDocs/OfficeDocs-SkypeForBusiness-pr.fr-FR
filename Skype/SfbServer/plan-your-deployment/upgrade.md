---
title: Planification de la mise à niveau vers Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Résumé : Découvrez les éléments que vous devez prendre en compte lors de la planification d’une mise à niveau vers Skype entreprise Server 2015. Téléchargez une version d’évaluation gratuite de Skype entreprise Server 2015 à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: 91cc78f22c03bf7ec59c9ac0c936f194ece71a35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030638"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planification de la mise à niveau vers Skype entreprise Server 2015
 
Résumé : Découvrez les éléments que vous devez prendre en compte lors de la planification d’une mise à niveau vers Skype entreprise Server 2015. Téléchargez une version d’évaluation gratuite de Skype entreprise Server 2015 à partir du centre d’évaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft à l’adresse suivante :.
  
Dans le cadre de votre plan de mise à niveau vers Skype entreprise Server 2015, utilisez cette rubrique pour comprendre les chemins de mise à niveau recommandés vers Skype entreprise Server 2015, le fonctionnement de la mise à niveau sur place, les scénarios de coexistence pris en charge et le processus de mise à niveau se présente comme suit.

> [!NOTE]
> Les mises à niveau sur place étaient disponibles dans Skype entreprise Server 2015, mais ne sont plus prises en charge dans Skype entreprise Server 2019. La coexistence côte à côte est prise en charge, reportez-vous à la rubrique [migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Chemins de mise à niveau recommandés vers Skype entreprise Server 2015

 Pour effectuer une mise à niveau à partir de Lync Server 2013, Lync Server 2010 ou Office Communications Server 2007 R2 vers Skype entreprise Server 2015, utilisez les chemins de mise à niveau suivants :
  
> [!CAUTION]
> La mise à niveau sur place déplace automatiquement les annuaires des conférences de Lync Server 2013 vers Skype entreprise Server 2015. Toutefois, si vous envisagez de déplacer manuellement des annuaires de conférence, il est très important d’utiliser Skype entreprise Server 2015 Management Shell. Si vous essayez d’utiliser Lync Server 2013 Management Shell pour déplacer des annuaires de conférence depuis Lync Server 2013 vers Skype entreprise Server 2015, une perte de données peut se produire. En règle générale, lorsque vous utilisez Skype entreprise Server 2015 en toute capacité, vous devez utiliser le jeu d’outils de l’outil Skype entreprise Server 2015.  
  
|**Version**|**Recommandations**|
|:-----|:-----|
|Lync Server 2013  <br/> | Pour effectuer une mise à niveau, utilisez le générateur de topologie Skype entreprise Server et la nouvelle fonctionnalité de mise à niveau sur place sur chacun des serveurs associés au pool. pour obtenir la procédure détaillée, voir [plan to Upgrade from Lync Server 2013 to Skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) et [Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) . <br/> |
|Lync Server 2010 + Lync Server 2013 (double mode)  <br/> |Tout d’abord, effectuez une mise à niveau vers Lync Server 2013, puis effectuez une mise à niveau vers Skype entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau sur place. Toutefois, si votre topologie est le serveur Lync Server 2010 principal, vous pouvez également restaurer les composants Lync Server 2013 sur Lync Server 2010, puis effectuer une mise à niveau directement vers Skype entreprise Server 2015. Dans ce cas, vous ne seriez pas en mesure de tirer parti de la mise à niveau sur place et d’utiliser la coexistence directe entre Lync Server 2010 et Skype entreprise Server 2015. L’absence de tri n’est pas prise en charge, mais la coexistence est prise en charge.  <br/> |
|Lync Server 2010  <br/> |Ouvrez un nouveau pool Skype entreprise Server 2015, puis migrez les utilisateurs vers ce nouveau pool. Vous pouvez ensuite mettre hors service l’ancien pool Lync Server 2010. La mise à niveau de Lync Server 2010 vers Skype entreprise Server 2015 est similaire à la mise à niveau de Lync Server 2010 vers Lync Server 2013. Consultez la rubrique [migration de Lync server 2010 vers Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Choisissez l’une des deux options suivantes : <br/>  Configurez un nouvel environnement Skype entreprise Server 2015. <br/>  Si votre matériel et votre logiciel satisfont à la configuration requise pour Skype entreprise Server 2015, effectuez une mise à niveau vers Lync Server 2013, puis vers Skype entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau sur place. Pour plus d’informations, reportez-vous à la rubrique [Server Requirements for Skype for Business server 2015](requirements-for-your-environment/server-requirements.md) et [migration from Office Communications Server 2007 R2 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 est pris en charge dans Skype entreprise Server 2015, mais n’est pas pris en charge dans Lync Server 2013. Si vous souhaitez effectuer une mise à niveau depuis SQL Server 2012 vers SQL Server 2014, le pool doit d’abord être mis à niveau vers Skype entreprise Server 2015 à l’aide de la méthode de mise à niveau sur place, comme décrit dans ce document. Vous pouvez ensuite effectuer la mise à niveau de SQL Server 2012 vers SQL Server 2014, consultez la rubrique [Upgrade to SQL server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx). Pour en savoir plus sur la configuration requise pour la base de données, consultez la rubrique [Server Requirements for Skype for Business server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planification de la mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Vous pouvez mettre à niveau les systèmes Lync Server 2013 vers Skype entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau sur place. La mise à niveau sur place offre une solution en un clic qui sauvegarde les certificats, désinstalle les composants serveur, met à niveau les bases de données locales et installe les rôles Skype entreprise Server 2015. La mise à niveau sur place permet de conserver les investissements de serveur et de matériel existants, réduisant le coût global de déploiement de Skype entreprise Server 2015.
  
> [!NOTE]
> La mise à niveau sur place vous permet d’utiliser le même matériel lors de la mise à niveau vers Skype entreprise Server. Toutefois, la réutilisation du même matériel ne se traduit pas dans la même capacité de performances. Vous ne devez pas vous attendre à ce que les charges de performances pour Lync Server 2013 et Skype entreprise Server 2015 soient identiques. 
  
> [!NOTE]
> La mise à niveau sur place ne prend pas en charge la haute disponibilité ou la récupération d’urgence pour Skype entreprise Server. 
  
La mise à niveau sur place consiste à mettre le pool Lync Server 2013 en mode hors connexion et à le mettre à niveau vers un pool Skype entreprise Server 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Créer un plan de mise à niveau sur place

Créez un plan qui inclut :
  
1. Une bonne compréhension de votre topologie actuelle.
    
    > [!NOTE]
    > Veillez à désinstaller l’outil d’administration LRS pour Lync Server 2013 avant d’exécuter la mise à niveau sur place. L’outil d’administration LRS pour Lync Server 2013 ne peut pas coexister avec Skype entreprise Server 2015. Après l’exécution de la mise à niveau sur place, installez le nouvel outil d’administration LRS. Pour plus d’informations, reportez-vous au [portail Web d’administration de Microsoft Lync Room System pour Skype entreprise Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) .
  
2. Le pool principal de la mise à niveau.
    
3. Si vous allez mettre à niveau les bases de données d’archivage et de surveillance ou en créer de nouvelles.
    
4. La méthode de mise à niveau sur place que vous utiliserez : Offline ou Move Users. Dans le cadre du déplacement des utilisateurs, vous devrez également migrer les annuaires de conférence globale associés au pool principal. 
    
5. Un plan de communication pour les utilisateurs affectés.
    
6. Un plan de sauvegarde en cas d’échec des mises à niveau.
    
Les utilisateurs qui se trouvent dans le pool principal alors qu’il est en cours de mise à niveau ne pourront pas utiliser les services tant que la mise à niveau n’est pas terminée. Si vous disposez d’un pool secondaire opérationnel, vous pouvez éviter d’influer sur les utilisateurs en les déplaçant vers le pool secondaire avant la mise à niveau. Après la mise à niveau, redéplacez les utilisateurs vers le pool principal.
  
### <a name="in-place-upgrade-methods"></a>Méthodes de mise à niveau sur place

Il existe deux scénarios pour la mise à niveau sur place : 
  
- La méthode Move User, qui ne nécessite aucun temps d’arrêt pour les utilisateurs. 
    
- La méthode hors ligne, qui nécessite un temps d’arrêt.
    
Nous vous recommandons de planifier une mise à niveau de méthode hors ligne pendant une période de maintenance et d’informer les utilisateurs du temps mort.
  
> [!NOTE]
> Lors de la mise à niveau d’un pool couplé sur Lync Server 2013 et que vous souhaitez mettre à niveau les deux pools vers Skype entreprise Server 2015. Assurez-vous de mettre à niveau le deuxième pool immédiatement après la mise à niveau du premier pool. Lorsqu’un pool exécute Lync Server 2013 et que le deuxième pool exécute Skype entreprise Server 2015, les options de récupération d’urgence sont réduites. Par exemple, si un pool exécute 2013 et le deuxième 2015 et qu’il y a un incident, vous pouvez alors être confronté à une perte de données, car le basculement de pool n’est pas pris en charge en mode de catastrophe lorsque les pools couplés ne sont pas de la même version. 
  
#### <a name="in-place-upgrade-offline-method"></a>Méthode hors connexion de mise à niveau sur place

Utilisez cette méthode si vous ne souhaitez pas déplacer les utilisateurs entre les pools d’utilisateurs. Lors de la mise à niveau, les utilisateurs ne peuvent pas utiliser les services Lync ou Skype entreprise. 
  
Le diagramme suivant présente une vue d’ensemble de ce processus.
  
![Lync 2013 pour les utilisateurs Skype hors connexion](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Si vous disposez de pools couplés, ne les découplez pas avant la mise à niveau. 
  
Une fois que vous avez commencé à mettre à niveau un pool de serveurs, vous devez effectuer la mise à niveau de l’ensemble du pool. Skype entreprise Server ne prend pas en charge la mise à niveau d’une seule partie du pool. 
  
#### <a name="move-users-method-no-user-downtime"></a>Move Users, méthode (aucun temps d’arrêt de l’utilisateur)
<a name="bkmk_MoveUsersMethod"> </a>

Pour utiliser cette méthode, vous devez déplacer les utilisateurs vers un autre pool avant de commencer la mise à niveau. Pendant la mise à niveau, les utilisateurs peuvent utiliser Lync services. Une fois qu’ils ont été déplacés vers le pool mis à niveau, ils peuvent utiliser Skype entreprise. Le diagramme suivant présente une vue d’ensemble de ce processus.
  
> [!IMPORTANT]
> Dans le cadre du déplacement des utilisateurs, vous devrez également migrer les annuaires de conférence globale associés au pool principal. La Conférence rendez-vous PSTN résoudra toujours ConferenceID dans le pool en cours de mise à niveau, au lieu du pool couplé. Par conséquent, vous devez déplacer les annuaires des conférences, si vous voulez que les conférences RTC planifiées dans le pool soient accessibles lors de la mise à niveau. 
  
![Diagramme de l’ensemble des utilisateurs déplacés vers un autre pool avant la mise à niveau du pool, après la mise à niveau du pool.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Déplacer des utilisateurs pour la mise à niveau matérielle
<a name="bkmk_MoveUsersMethod"> </a>

 Si votre matériel ne dispose pas [de la configuration requise pour Skype entreprise server 2015](requirements-for-your-environment/server-requirements.md), configurez un nouvel environnement Skype entreprise Server 2015 et déplacez-y les utilisateurs. Le diagramme suivant présente une vue d’ensemble de ce processus de mise à niveau à partir de Lync Server 2010. 
  
![Diagramme de couloir d’activité qui montre les utilisateurs du pool frontal principal Lync Server déplacé vers Skype entreprise Server 2015 et le pool Lync Server en cours de désactivation.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Processus de mise à niveau sur place

 Effectuez la mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015 en procédant comme suit :
  
1. Sauvegardez toutes les bases de données avant la mise à niveau.
    
2. Assurez-vous que tous les services qui doivent être mis à niveau sont en cours d’exécution.
    
3. Mettez à niveau et publiez le fichier de topologie à l’aide du générateur de topologie.
    
4. Arrêtez tous les services sur tous les serveurs frontaux.
    
5. Installez les nouvelles conditions préalables requises pour Skype entreprise Server.
    
6. Sur chaque serveur frontal, démarrez la mise à niveau sur place.
    
7. Une fois la mise à niveau terminée, redémarrez tous les services.
    
   - Pour le pool frontal, redémarrez les services à l’aide de la commande Start-applet cspool.
    
   - Pour les serveurs non frontaux, utilisez Start-CSWindowsService.
    
> [!NOTE]
>  Si vous ne souhaitez pas mettre à niveau vos bases de données d’archivage et de surveillance existantes, supprimez la dépendance avant de procéder à la mise à niveau de la topologie. Si vous souhaitez créer de nouvelles bases de données d’archivage et de surveillance, lors de la mise à niveau, vous pouvez créer un nouveau magasin SQL et l’associer au pool. Vous trouverez les étapes à suivre dans la rubrique[mise à niveau vers Skype entreprise Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > la mise à niveau sur place ne prend pas en charge la haute disponibilité ou la récupération d’urgence pour Skype entreprise Server. Pour éviter d’interrompre les services des utilisateurs, utilisez la [méthode Move Users (sans temps d’arrêt de l’utilisateur)](upgrade.md#bkmk_MoveUsersMethod) pour effectuer la mise à niveau. > lors du processus de mise à niveau le réplica XDS est placé dans le dossier partagé local sur le lecteur de disque doté de la plus grande quantité d’espace libre. Si ce disque est supprimé par la suite, vous pouvez rencontrer des problèmes tels que les services qui ne démarrent pas.
  
### <a name="upgrade-order"></a>Ordre de mise à niveau

Mettez à niveau la topologie de l’intérieur vers l’extérieur. Commencez par mettre à niveau tous vos pools, puis les serveurs Edge et enfin le pool de magasin central de gestion (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Considérations relatives à l’authentification Kerberos

Si vous utilisez l’authentification Kerberos pour les services Web, vous devez réaffecter les comptes Kerberos et réinitialiser le mot de passe une fois la mise à niveau sur place terminée. Pour savoir comment procéder, consultez la rubrique [configuration de l’authentification Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Prise en charge de la coexistence avec Lync Server 2013 et Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Vous pouvez exécuter Skype entreprise Server 2015 dans la même topologie que Lync Server 2013 ou Lync Server 2010, mais vous ne pouvez pas avoir les trois dans la même topologie.
  
Si vous avez une coexistence entre Lync Server 2010 et Lync Server 2013, il est recommandé de mettre à niveau la topologie complète vers Lync Server 2013, puis de procéder à la mise à niveau vers Skype entreprise Server 2015 à l’aide de la mise à niveau sur place. Pour plus d’informations, consultez la rubrique [migration de Lync server 2010 vers Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Si votre topologie est principalement Lync Server 2010, restaurez les composants Lync Server 2013 sur Lync Server 2010 avant de mettre à niveau la topologie vers Skype entreprise Server 2015. Dans ce cas, vous perdez le bénéfice de la mise à niveau sur place et vous disposez d’une topologie de coexistence entre Lync Server 2010 et Skype entreprise Server 2015.
  
Le diagramme suivant montre la prise en charge de la coexistence de Skype entreprise Server 2015 avec Lync Server 2013 et Lync Server 2010.
  
![Diagramme illustrant la prise en charge de la coexistence pour Skype entreprise Server 2015 avec Lync Server 2013 ou Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Processus de mise à niveau avec le Survivable Branch appliance et le serveur Survivable Branch Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype entreprise Server 2015 ne prend pas en charge la mise à niveau sur place d’un Survivable Branch Appliance (SBA) ou d’un serveur Survivable Branch Server (SBS).
  
Toutefois, nous prenons en charge la coexistence des centres de serveurs Skype entreprise Server avec Lync Server 2010 ou Lync Server 2013 SBA/SBS. 
  
Lors de la planification d’une mise à niveau sur place d’un pool de serveurs frontaux (FE) Lync Server 2013 avec une branche associée, vous pouvez laisser les utilisateurs existants sur Lync Server 2013 SBA/SBS. Lors de la mise à niveau, les utilisateurs SBA/SBS passent en mode résistance et retournent à la fonctionnalité normale une fois la mise à niveau terminée. Pour plus d’informations sur l’expérience utilisateur en mode résistance, reportez-vous à la rubrique [fonctionnalités de résistance de site de succursale dans Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Lors de la migration d’une topologie Lync Server 2010 vers Skype entreprise Server 2015, le SBA/SBS doit de nouveau être ajouté à la topologie, de la même manière que pour la migration vers Lync Server 2013. Pour les étapes requises, consultez la partie [Connecting Survivable Branch Appliance to Lync Server 2013 front end pool](https://technet.microsoft.com/library/jj688026.aspx).
  
Pour les topologies de coexistence de Lync Server 2010 et Lync Server 2013, alignez tout d’abord les recommandations formulées dans la section « prise en charge de la coexistence avec Lync Server 2013 et Lync Server 2010 ».
  
## <a name="see-also"></a>Voir aussi
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Mise à niveau vers Skype entreprise Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Configuration environnementale requise pour Skype entreprise Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Configuration requise pour le serveur pour Skype entreprise Server 2015](requirements-for-your-environment/server-requirements.md)

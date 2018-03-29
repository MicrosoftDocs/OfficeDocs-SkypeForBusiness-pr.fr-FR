---
title: Plan de mise à niveau vers Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Résumé : Découvrez les choses que vous devez considérer lorsque vous planifiez une mise à niveau Skype Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 81ab68c2fc128016d83962894074c0771e2977d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Plan de mise à niveau vers Skype Entreprise Server 2015
 
Résumé : Découvrez les choses que vous devez considérer lorsque vous planifiez une mise à niveau Skype Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour 2015 de serveur d’entreprise depuis le centre d’évaluation Microsoft à : [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Dans le cadre de votre plan de mise à niveau vers Skype pour Business Server 2015, utilisez cette rubrique pour comprendre comment les chemins de mise à niveau recommandées vers Skype pour 2015 de serveur d’entreprise, les travaux de mise à niveau sur Place, quels sont les scénarios de coexistence pris en charge et que le processus de mise à niveau l’aspect.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Chemins de mise à niveau recommandées à Skype pour Business Server 2015

 Pour mettre à niveau à partir de Lync Server 2013, Lync Server 2010 ou Office Communications Server 2007 R2 Skype pour Business Server 2015, utilisez les chemins de mise à niveau suivants :
  
> [!CAUTION]
> La mise à niveau sur place met automatiquement à jour les répertoires de conférences de Lync Server 2013 vers Skype Entreprise Server 2015. Cependant, si vous envisagez d’effectuer cette procédure manuellement, il est important d’utiliser Skype Entreprise Server 2015 Management Shell. Si vous tentez d’utiliser Lync Server 2013 Management Shell pour effectuer la mise à niveau des répertoires de conférence de Lync Server 2013 vers Skype Entreprise Server 2015, vous risquez de perdre des données. En général, dès que vous travaillez avec Skype Entreprise 2015, quelle que soit la capacité, vous devez vous servir des outils Skype Entreprise Server 2015. 
  
|**Version**|**Recommandations**|
|:-----|:-----|
|Lync Server 2013  <br/> | Pour mettre à niveau, utilisez le Skype pour le Générateur de topologies Business Server et la nouvelle fonctionnalité de mise à niveau sur Place sur chacun des serveurs associés au pool. Pour obtenir la procédure détaillée, reportez-vous à la section [mise à niveau à partir de Lync Server 2013 à Skype pour Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) et [mise à niveau vers Skype pour Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) . <br/> |
|Lync Server 2010 + Lync Server 2013 (mode double)  <br/> |Tout d’abord mettre à niveau vers Lync Server 2013 et ensuite à jour Skype pour 2015 de serveur d’entreprise à l’aide de la nouvelle fonctionnalité de mise à niveau sur Place. En revanche, si votre topologie principale est Lync Server 2010, vous pouvez également rétrograder les composants Lync Server 2013 vers Lync Server 2010, puis mettre à niveau directement vers Skype Entreprise Server 2015. Dans ce cas, vous ne pourrez pas tirer parti de la mise à niveau sur place et utiliserez directement la coexistence entre Lync Server 2010 et Skype Entreprise Server 2015. La tri-existence n’est pas prise en charge, mais la coexistence l’est.  <br/> |
|Lync Server 2010  <br/> |Ouvrez un nouveau pool Skype Entreprise Server 2015, puis faites migrer les utilisateurs vers ce nouveau pool. Vous pouvez ensuite désactiver l’ancien pool Lync Server 2010. Une mise à niveau de Lync Server 2010 vers Skype Entreprise Server 2015 s’apparente à une mise à niveau de Lync Server 2010 vers Lync Server 2013. Reportez-vous à la section [Migration de Lync Server 2010 à Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Choisissez une des deux options : <br/>  Permet de paramétrer un nouveau Skype pour environnement d’entreprise serveur 2015. <br/>  Ou si votre matériel et vos logiciels répondent à la configuration requise pour Skype pour Business Server 2015, mise à niveau vers Lync Server 2013, puis mise à niveau vers Skype pour 2015 de serveur d’entreprise à l’aide de la nouvelle fonctionnalité de mise à niveau sur Place. Pour plus d’informations, reportez-vous à la section [configuration du serveur pour Skype pour Business Server 2015](requirements-for-your-environment/server-requirements.md) et [Migration à partir d’Office Communications Server 2007 R2 vers Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> 2014 de SQL Server est pris en charge dans Skype pour Business Server 2015, mais n’est pas pris en charge dans Lync Server 2013. Si vous souhaitez mettre à niveau SQL Server 2012 vers SQL Server 2014 puis le pool doit tout d’abord être mis à niveau vers Skype pour 2015 de serveur d’entreprise à l’aide de la méthode de mise à niveau sur Place comme décrit dans ce document. Vous pouvez ensuite mettre à niveau à partir de SQL Server 2012 à 2014 de SQL Server, consultez [mise à niveau vers SQL Server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx). Pour en savoir plus sur les conditions de la base de données, reportez-vous à la section [configuration serveur requise pour Skype pour Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planifier une mise à niveau à partir de Lync Server 2013 vers Skype Entreprise Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Vous pouvez mettre à niveau des systèmes de Lync Server 2013 à Skype pour 2015 de serveur d’entreprise à l’aide de la nouvelle fonctionnalité de mise à niveau sur Place. Mise à niveau fournit une solution d’un seul clic qui sauvegarde des certificats, désinstalle les composants serveur, met à niveau les bases de données locales et installe le Skype pour les rôles d’entreprise serveur 2015. Mise à niveau vise à préserver le matériel existant et les investissements dans les serveurs, réduisant le coût total pour déployer Skype pour Business Server 2015.
  
> [!NOTE]
> La mise à niveau sur Place vous permet d’utiliser le même matériel lors de la mise à niveau vers Skype pour Business Server. Toutefois, en réutilisant la même configuration matérielle, vous n’obtenez pas la même capacité en termes de performances. Vous devriez pas les charges de performances pour Lync Server 2013 et Skype pour Business Server 2015 doivent être identiques. 
  
> [!NOTE]
> Mise à niveau ne supporte pas les haute disponibilité ou récupération d’urgence pour Skype pour Business Server. 
  
Mise à niveau consiste à déconnecter le pool Lync Server 2013 et la mise à niveau pour un Skype pour le pool d’entreprise serveur 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Créer un plan de mise à niveau sur place

Créer un plan qui inclut :
  
1. Comprendre votre topologie actuelle.
    
    > [!NOTE]
    > Veillez à désinstaller l’outil d’administration de LRS de Lync Server 2013 avant d’exécuter la mise à niveau sur Place. L’outil d’administration de Lync Server 2013 LRS ne peuvent pas coexister avec Skype pour Business Server 2015. Après l’exécution de la mise à niveau sur Place, installer le nouvel outil d’administration de LRS, voir la rubrique [Microsoft Lync salle de système d’administration Web Portal pour Skype pour Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807)
  
2. Le pool principal pour la mise à niveau.
    
3. Déterminez si vous allez mettre à niveau les bases de données d’archivage et de surveillance ou en créer de nouvelles.
    
4. La méthode de mise à niveau sur place que vous utiliserez : Hors ligne ou Déplacer les utilisateurs. Avec le déplacement des utilisateurs, vous devrez également assurer la migration des annuaires des conférences globaux associés au pool principal. 
    
5. Un plan de communication pour les utilisateurs concernés.
    
6. Un plan de sauvegarde en cas d’échec de la mise à niveau.
    
Tous les utilisateurs qui sont dans le pool principal alors que celui-ci est en cours de mise à niveau ne seront pas en mesure d’utiliser les services tant que la mise à niveau n’est pas terminée. Si vous avez un pool secondaire opérationnel, vous pouvez éviter tout impact sur les utilisateurs en les déplaçant vers le pool secondaire avant la mise à niveau. Après la mise à niveau, déplacez les utilisateurs vers le pool principal.
  
### <a name="in-place-upgrade-methods"></a>Méthodes de mise à niveau sur place

Il existe deux scénarios pour la mise à niveau sur place : 
  
- La méthode Déplacer l’utilisateur, qui évite d’avoir un temps d’arrêt pour les utilisateurs. 
    
- La méthode Hors ligne, qui nécessite un temps d’arrêt.
    
Nous vous recommandons que planifier une mise à niveau de la méthode hors connexion pendant une période de maintenance, et les utilisateurs sont avertis de l’indisponibilité.
  
> [!NOTE]
> Lorsque vous mettez à niveau un pool associé sur Lync Server 2013 et que vous voulez mettre à niveau les deux pools vers Skype Entreprise Server 2015, veillez à mettre le deuxième pool à niveau tout de suite après la mise à niveau du premier pool. Lorsqu’un pool exécute Lync Server 2013 et que le deuxième pool exécute Skype Entreprise Server 2015, les options de récupération d’urgence sont réduites. Par exemple, si le premier pool exécute la version 2013 et le second, la version 2015 et qu’un sinistre se produit, vous risquez de perdre des données, car le basculement de pool n’est pas pris en charge en mode de récupération d’urgence lorsque les pools associés n’utilisent pas la même version. 
  
#### <a name="in-place-upgrade-offline-method"></a>Méthode de mise à niveau sur place Hors ligne

Utilisez cette méthode si vous ne souhaitez pas déplacer d’utilisateurs entre des pools d’utilisateurs. Au cours de la mise à niveau, les utilisateurs ne sera pas en mesure d’utiliser Lync ou Skype pour les services. 
  
Le diagramme suivant présente une vue d’ensemble du processus.
  
![Lync 2013 aux utilisateurs Skype hors ligne](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Si vous avez des pools associés, ne les dissociez pas avant la mise à niveau. 
  
Une fois que vous avez commencé à mettre à niveau le pool de serveurs, vous devez compléter la mise à niveau du pool tout entier. Skype pour Business Server ne prend en charge qu’une partie de la liste des mises à niveau. 
  
#### <a name="move-users-method-no-user-downtime"></a>Méthode Déplacer les utilisateurs (aucun temps d’arrêt)
<a name="bkmk_MoveUsersMethod"> </a>

Pour utiliser cette méthode, déplacez les utilisateurs vers un autre pool avant de commencer la mise à niveau. Au cours de la mise à niveau, les utilisateurs peuvent utiliser les services de Lync. Une fois qu’elles sont placées dans le pool de mise à niveau, ils peuvent utiliser Skype pour les entreprises. Le diagramme suivant montre une vue d’ensemble de ce processus.
  
> [!IMPORTANT]
> Dans le cadre du déplacement des utilisateurs, vous devrez également effectuer une migration des annuaires des conférences globaux liés au pool principal. Les conférences rendez-vous PSTN résoudront toujours ConferenceID au pool mis à niveau au lieu de le faire avec le pool associé. De ce fait, vous devez déplacer les annuaires des conférences si vous souhaitez toujours que les conférences PSTN planifiées dans le pool soient accessibles pendant la mise à niveau. 
  
![Organigramme représentant le déplacement d’utilisateurs vers un autre pool avant que leur pool d’origine ne soit mis à niveau, puis leur réintégration dans ce même pool après la mise à niveau.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Déplacer des utilisateurs pour la mise à niveau matérielle
<a name="bkmk_MoveUsersMethod"> </a>

 Si votre matériel ne répond pas à [configuration du serveur pour Skype pour Business Server 2015](requirements-for-your-environment/server-requirements.md), définir un nouveau Skype pour environnement d’entreprise serveur 2015 et y déplacer les utilisateurs. Le diagramme suivant montre une vue d’ensemble de ce processus dans le cadre d’une mise à niveau à partir de Lync Server 2010. 
  
![Organigramme représentant le passage des utilisateurs du pool frontal principal Lync Server vers Skype Entreprise Server 2015 et le pool Lync Server en cours de désaffection.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Processus de mise à niveau sur place

 Mise à niveau à partir de Lync Server 2013 à Skype pour Business 2015 de serveur à l’aide des étapes suivantes :
  
1. Sauvegardez toutes les bases de données avant la mise à niveau.
    
2. Assurez-vous que tous les services qui doivent être mis à niveau sont en état de fonctionner.
    
3. Mettez à niveau et publiez le fichier de topologie en utilisant le Générateur de topologie.
    
4. Arrêtez tous les services sur tous les serveurs frontaux.
    
5. Installer les nouveaux composants requis nécessaires pour Skype pour Business Server.
    
6.  Sur chaque serveur frontal, lancez la mise à niveau sur place.
    
7. Lorsque la mise à niveau est terminée, redémarrez tous les services.
    
  - Pour le pool frontal, redémarrez les services en utilisant la commande Start-CsPool.
    
  - Pour les serveurs frontaux, utilisez Start-CSWindowsService.
    
> [!NOTE]
>  Si vous ne souhaitez pas mettre à niveaux vos bases de données d’archivage et de surveillance existants, supprimez la dépendance avant la mise à niveau de la topologie. Si vous voulez créer de nouvelles bases de données de surveillance et d’archivage, lors de la mise à niveau, vous pouvez créer un nouveau magasin SQL et l’associer au pool. Vous trouverez les étapes de cette procédure dans la rubrique[mise à niveau vers Skype pour Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > Mise à niveau ne supporte pas haute disponibilité et reprise après sinistre pour Skype pour Business Server. Pour éviter d’interrompre les services des utilisateurs, utilisez la [méthode de déplacer des utilisateurs (sans interruption de l’utilisateur)](upgrade.md#bkmk_MoveUsersMethod) pour la mise à niveau. > au cours du processus de mise à niveau, le réplica de xds est placé dans le dossier partagé local sur le disque avec le plus grand espace libre. Si ce disque est supprimé par la suite, vous pouvez rencontrer des problèmes, comme des services qui ne démarrent pas.
  
### <a name="upgrade-order"></a>Séquence de la mise à niveau

Mettre à niveau la topologie à partir de l’intérieur vers l’extérieur. Mettez à niveau tous vos pools d’abord, puis les serveurs de périphérie, et enfin le pool CMS (Central Management Store). 
  
### <a name="kerberos-authentication-considerations"></a>Considérations à propos de l’authentification Kerberos

Si vous utilisez l’authentification Kerberos pour les services web, vous devez réattribuer des comptes Kerberos et réinitialiser le mot de passe une fois la mise à niveau sur place terminée. Pour savoir comment procéder, reportez-vous à la section [configuration de l’authentification Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Prise en charge de la coexistence avec Microsoft Lync Server 2013 et Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Il est possible d’exécuter Skype Entreprise Server 2015 au sein de la même topologie que Lync Server 2013 ou que Lync Server 2010, mais il n’est pas possible d'avoir les trois à la fois dans la même topologie.
  
Si Lync Server 2010 coexiste avec Lync Server 2013, nous vous recommandons une mise à niveau de toute la topologie vers Lync Server 2013, puis une mise à niveau vers Skype Entreprise Server 2015 grâce à la nouvelle fonctionnalité de mise à niveau sur place. Pour plus d’informations, consultez [Migration de Lync Server 2010 à Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Si votre topologie principale est Lync Server 2010, rétrogradez les composants Lync Server 2013 vers Lync Server 2010, avant de mettre à niveau la topologie vers Skype Entreprise Server 2015. Dans ce cas, vous perdrez les avantages de la mise à niveau sur place et vous aurez une topologie de coexistence entre Lync Server 2010 et Skype Entreprise Server 2015.
  
Le diagramme suivant illustre la prise en charge de coexistence de Skype pour 2015 de serveur d’entreprise avec Lync Server 2013 et Lync Server 2010.
  
![Diagramme présentant la prise en charge de la coexistence de Skype Entreprise Server 2015 avec Lync Server 2013 et Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Processus de mise à niveau avec version existante de Survivable Branch Appliance et Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype pour Business Server 2015 ne prend pas en charge une mise à niveau sur Place d’une solution matérielle-logicielle de branche Survivable (SBA) ou Survivable Branch Server (SBS).
  
Cependant, la coexistence des centres de données Skype Entreprise Server avec Lync Server 2010 ou Lync Server 2013 SBA/SBS est prise en charge. 
  
Lors de la planification de la mise à niveau sur place d’un pool frontal Lync Server 2013 avec une succursale associée, vous pouvez laisser les utilisateurs existants sur le SBA/SBS Lync Server 2013. Pendant la mise à niveau, les utilisateurs SBA/SBS seront placés en mode résistance, et récupèreront des fonctionnalités normales à la fin de la mise à niveau. Pour plus d’informations sur l’expérience des utilisateurs au cours du mode de résilience, veuillez consulter le [site de la succursale les fonctionnalités de résilience dans Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Lors de la migration d’une topologie Lync Server 2010 vers Skype Entreprise Server 2015, le SBA/SBS doit être ajouté à nouveau à la topologie, d’une manière similaire à une migration vers Lync Server 2013. Pour les étapes à suivre, lisez la [Connexion Survivable Branch Appliance au pool de Lync Server 2013 Front-End](https://technet.microsoft.com/library/jj688026.aspx).
  
Pour la coexistence de topologies de Lync Server 2010 et Lync Server 2013, Aligner en premier les recommandations formulées dans la section « Prise en charge pour la coexistence avec Microsoft Lync Server 2013 et Lync Server 2010 ».
  
## <a name="see-also"></a>Voir aussi
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

#### 

[Mise à niveau vers Skype pour Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Besoins environnementaux dans Skype pour Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Configuration serveur requise pour Skype pour Business Server 2015](requirements-for-your-environment/server-requirements.md)


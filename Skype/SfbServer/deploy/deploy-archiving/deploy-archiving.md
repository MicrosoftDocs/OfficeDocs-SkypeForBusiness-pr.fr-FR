---
title: Déployer l’archivage pour Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Résumé : Lisez cette rubrique pour savoir comment déployer l’archivage pour Skype pour Business Server.'
ms.openlocfilehash: 0598d1a35523cc38d85320206b065b85e025687e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233216"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Déployer l’archivage pour Skype pour Business Server
 
**Résumé :** Lisez cette rubrique pour savoir comment déployer l’archivage pour Skype pour Business Server.
  
L’archivage est installé automatiquement sur chaque serveur frontal dans votre Skype pour le déploiement de serveur d’entreprise, mais vous devez effectuer les étapes de configuration et de configuration initiale avant de pouvoir l’utiliser. Avant de commencer, assurez-vous que vous êtes familiarisé avec les concepts de [planification de l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Liste de contrôle du déploiement

La manière de configurer l’archivage dépend de l’option de stockage choisie : 
  
- Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs dans votre déploiement, vous n’avez pas besoin de configurer Skype pour les stratégies d’archivage Business Server pour vos utilisateurs. Au lieu de cela, vous configurez des stratégies de blocage sur Place Exchange pour prendre en charge l’archivage pour les utilisateurs hébergés sur Exchange, avec leurs boîtes aux lettres mettre en blocage sur Place. Pour plus d’informations sur la configuration de ces stratégies, voir la documentation du produit Exchange.
    
- Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs dans votre déploiement, vous devez ajouter Skype pour Business Server d’archivage de bases de données (bases de données SQL Server) à votre topologie, publier la topologie mise à jour et puis configurer les stratégies d’archivage et paramètres de vos utilisateurs. Vous pouvez déployer les bases de données d’archivage en même temps que la topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition. Ce document indique la marche à suivre pour déployer des bases de données d’archivage en les ajoutant à un déploiement existant.
    
Si vous activez l’archivage sur un pool frontal ou un serveur Standard Edition, vous devez l’activer pour tous les pools frontaux et serveurs Standard Edition dans le déploiement. Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée. Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.
  
> [!IMPORTANT]
> Si l’archivage est essentiel au sein de votre organisation pour des raisons de conformité, veillez à déployer l’archivage, configurer des stratégies et autres options au niveau approprié, puis activer l’archivage pour tous les utilisateurs appropriés, avant d’activer les utilisateurs pour Skype pour Serveur d’entreprise. 
  
Le tableau ci-dessous décrit les étapes nécessaires pour déployer l’archivage dans une topologie existante.
  
|**Phase**|**Étapes**|**Rôles et appartenance aux groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> |Pour utiliser l’intégration de Microsoft Exchange (à l’aide d’Exchange pour le stockage d’archivage pour certains ou tous les utilisateurs), vous avez besoin d’un déploiement Exchange existant.  <br/> Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour le stockage d’archives d’une partie ou de la totalité des utilisateurs, vous avez besoin de SQL Server sur le serveur qui va stocker les données d’archivage.  <br/> L’archivage s’exécute sur les serveurs frontaux d’un pool Enterprise et des serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Planifier l’intégration de Skype Entreprise et d’Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Configuration système requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Créer la topologie interne appropriée pour prendre en charge l’archivage (uniquement si vous n’utilisez ne pas de l’intégration de Microsoft Exchange pour tous les utilisateurs dans votre déploiement)** <br/> |Exécuter le Générateur de topologie pour ajouter Skype pour Business Server d’archivage de bases de données (bases de données SQL Server) à la topologie, puis publiez la topologie.  <br/> |Pour définir une topologie afin qu’elle intègre des bases de données d’archivage, un compte membre du groupe Utilisateurs local est requis.  <br/> Pour publier la topologie, un compte qui est membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations Contrôle total (lecture/écriture/modifier) sur le partage de fichiers à utiliser pour le Skype pour le magasin de fichiers Business Server (afin que la topologie Le Générateur de peut configurer les DACL requis).  <br/> |[Ajouter des bases de données d’archivage à un déploiement existant dans Skype pour Business Server](add-archiving-databases.md) <br/> |
|**Configurer l’authentification de serveur à serveur (uniquement si l’intégration de Microsoft Exchange)** <br/> |Configurer des serveurs pour activer l’authentification entre Skype pour Business Server et Exchange. Nous vous recommandons d’exécution **Test-CsExchangeStorageConnectivity testuser_sipUri-dossier benne** pour valider l’archivage de connectivité de stockage avant d’activer l’archivage de Exchange. <br/> |Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.  <br/> |Gérer l’authentification de serveur à serveur  <br/> |
|**Configurer les stratégies et les options d’archivage** <br/> |Configurer l’archivage, notamment si vous souhaitez utiliser l’intégration de Microsoft Exchange, la stratégie globale et les stratégies de site et d’utilisateur (si vous N'utilisez pas l’intégration de Microsoft Exchange pour le stockage des données) et l’archivage des options, telles que mode critique et des données le vidage et exportation.  <br/> Si vous utilisez l’intégration de Microsoft Exchange, configurez les stratégies de blocage sur Place Exchange comme il convient.  <br/> |Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.  <br/> |[Configurer les options d’archivage pour Skype pour Business Server](configure-archiving-options.md) <br/> Exchange documentation du produit (si l’intégration de Microsoft Exchange).  <br/> |
   


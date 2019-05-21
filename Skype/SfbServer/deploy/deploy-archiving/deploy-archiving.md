---
title: Déploiement de l’archivage pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Résumé: cette rubrique vous explique comment déployer l’archivage pour Skype entreprise Server.'
ms.openlocfilehash: 813911dba5bfc662ee1c6bea9dab99e34c031e98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286528"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Déploiement de l’archivage pour Skype entreprise Server
 
**Résumé:** Pour plus d’informations sur le déploiement de l’archivage dans Skype entreprise Server, voir cette rubrique.
  
L’archivage est automatiquement installé sur chaque serveur frontal dans le déploiement de Skype entreprise Server, mais vous devez toujours effectuer les étapes de configuration et de configuration pour pouvoir l’utiliser. Avant de commencer, assurez-vous que vous connaissez les concepts de la planification de l' [archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Liste de contrôle du déploiement

La manière de configurer l’archivage dépend de l’option de stockage choisie : 
  
- Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer les stratégies d’archivage de Skype entreprise Server pour vos utilisateurs. Au lieu de cela, vous configurez les stratégies de conservation inaltérable pour la prise en charge de l’archivage pour les utilisateurs hébergés sur Exchange, et leurs boîtes aux lettres sont placées dans la conservation inaltérable. Pour plus d’informations sur la configuration de ces stratégies, voir la documentation du produit Exchange.
    
- Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez ajouter des bases de données d’archivage Skype entreprise Server (bases de données SQL Server) à votre topologie, publier la topologie mise à jour, puis configurer les stratégies d’archivage et paramètres de vos utilisateurs. Vous pouvez déployer les bases de données d’archivage en même temps que la topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition. Ce document indique la marche à suivre pour déployer des bases de données d’archivage en les ajoutant à un déploiement existant.
    
Si vous activez l’archivage sur un pool frontal ou un serveur Standard Edition, vous devez l’activer pour tous les pools frontaux et serveurs Standard Edition dans le déploiement. Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée. Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.
  
> [!IMPORTANT]
> Dans le cas où l’archivage est essentiel au sein de votre organisation pour des raisons de conformité, n’oubliez pas de déployer l’archivage, de configurer les stratégies et d’autres options au niveau approprié, puis de réactiver l’archivage pour tous les utilisateurs appropriés avant d’activer ces utilisateurs pour Skype. Business Server. 
  
Le tableau ci-dessous décrit les étapes nécessaires pour déployer l’archivage dans une topologie existante.
  
|**Phase**|**Étapes**|**Rôles et appartenance aux groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> |Pour utiliser l’intégration de Microsoft Exchange (à l’aide d’Exchange pour le stockage d’archivage pour tout ou partie des utilisateurs), vous avez besoin d’un déploiement Exchange existant.  <br/> Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour le stockage d’archives d’une partie ou de la totalité des utilisateurs, vous avez besoin de SQL Server sur le serveur qui va stocker les données d’archivage.  <br/> L’archivage s’exécute sur les serveurs frontaux d’un pool Enterprise et des serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Planifier l’intégration de Skype Entreprise et d’Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Configuration système requise pour Skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Créez la topologie interne appropriée pour la prise en charge de l’archivage (uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement).** <br/> |Exécutez le générateur de topologie pour ajouter des bases de données d’archivage de Skype entreprise Server (bases de données SQL Server) à la topologie, puis publiez la topologie.  <br/> |Pour définir une topologie afin qu’elle intègre des bases de données d’archivage, un compte membre du groupe Utilisateurs local est requis.  <br/> Pour publier la topologie, un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le stockage de fichiers Skype entreprise Server (de sorte que cette topologie Le générateur peut configurer les DACL nécessaires.  <br/> |[Ajouter des bases de données d’archivage à un déploiement existant dans Skype entreprise Server](add-archiving-databases.md) <br/> |
|**Configurer l’authentification de serveur à serveur (uniquement si vous utilisez l’intégration de Microsoft Exchange)** <br/> |Configurer les serveurs pour activer l’authentification entre Skype entreprise Server et Exchange. Nous vous recommandons d’exécuter **test-CsExchangeStorageConnectivity testuser_sipUri-Folder benne** pour valider la connectivité de stockage d’archivage Exchange avant de procéder à l’archivage. <br/> |Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.  <br/> |Gérer l’authentification de serveur à serveur  <br/> |
|**Configurer les stratégies et les options d’archivage** <br/> |Configuration de l’archivage, y compris l’utilisation de l’intégration de Microsoft Exchange, de la stratégie globale et des stratégies de site et d’utilisateur (si vous n’utilisez pas l’intégration de Microsoft Exchange pour tout le stockage des données) et des options d’archivage spécifiques, telles que le mode et les données critiques exportation et suppression définitive.  <br/> Dans le cadre de l’utilisation de l’intégration de Microsoft Exchange, configurez les stratégies de blocage sur place Exchange, le cas échéant.  <br/> |Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.  <br/> |[Configurer les options d’archivage de Skype entreprise Server](configure-archiving-options.md) <br/> Documentation du produit Exchange (si vous utilisez l’intégration de Microsoft Exchange).  <br/> |
   


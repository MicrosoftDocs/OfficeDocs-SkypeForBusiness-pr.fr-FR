---
title: Déployer l’archivage de Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Résumé : Lisez cette rubrique pour savoir comment déployer l’archivage pour Skype pour Business Server 2015.'
ms.openlocfilehash: d218c59038b599f016f99cbce453f0bf1830a6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-archiving-for-skype-for-business-server-2015"></a>Déployer l’archivage de Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment déployer l’archivage pour Skype pour Business Server 2015.
  
L’archivage est automatiquement installé sur chaque serveur frontal dans votre Skype pour le déploiement de Business Server 2015, mais vous devrez effectuer la configuration initiale et des étapes de configuration avant de pouvoir l’utiliser. Avant de commencer, assurez-vous que vous êtes familiarisé avec les concepts de [planification de l’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Liste de contrôle du déploiement

La manière de configurer l’archivage dépend de l’option de stockage choisie : 
  
- Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs dans votre déploiement, vous n’avez pas besoin de configurer Skype pour les stratégies d’archivage de Business Server pour les utilisateurs. Au lieu de cela, vous configurez contenir de Exchange Place des stratégies pour prendre en charge de l’archivage pour les utilisateurs hébergés sur Exchange, avec leurs boîtes aux lettres mis en Place maintenez. Pour plus d’informations sur la configuration de ces stratégies, consultez la documentation du produit Exchange.
    
- Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs dans votre déploiement, vous avez besoin d’ajouter Skype pour Business Server, archivage des bases de données (bases de données SQL Server) dans votre topologie, publiez la topologie mis à jour et puis configurer les stratégies d’archivage et paramètres de vos utilisateurs. Vous pouvez déployer les bases de données d’archivage en même temps que la topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition. Ce document indique la marche à suivre pour déployer des bases de données d’archivage en les ajoutant à un déploiement existant.
    
Si vous activez l’archivage sur un pool frontal ou un serveur Standard Edition, vous devez l’activer pour tous les pools frontaux et serveurs Standard Edition dans le déploiement. Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée. Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.
  
> [!IMPORTANT]
> Si l’archivage est critique dans votre organisation pour des raisons de conformité, veillez à déployer d’archivage, de configurer des stratégies et autres options au niveau approprié et puis activer l’archivage pour tous les utilisateurs appropriés, avant de vous permettre à ces utilisateurs de Skype pour Serveur d’entreprise. 
  
Le tableau ci-dessous décrit les étapes nécessaires pour déployer l’archivage dans une topologie existante.
  
|**Phase de**|**Étapes**|**Rôles et appartenances aux groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> |Pour utiliser l’intégration de Microsoft Exchange (à l’aide d’Exchange pour le stockage d’archivage pour certains ou tous les utilisateurs), vous avez besoin d’un déploiement Exchange existant.  <br/> Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour le stockage d’archives d’une partie ou de la totalité des utilisateurs, vous avez besoin de SQL Server sur le serveur qui va stocker les données d’archivage.  <br/> L’archivage s’exécute sur les serveurs frontaux d’un pool Enterprise et des serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |[Configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Besoins environnementaux dans Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Configuration matérielle et logicielle pour l’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/hardware-and-software-requirements.md) <br/> [Planifier l’intégration de Skype pour les entreprises et Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/> |
|**Création de la topologie interne appropriée pour prendre en charge de l’archivage (uniquement si vous N'utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs dans votre déploiement)** <br/> |Exécuter le Générateur de topologies pour ajouter Skype pour l’archivage des bases de données (SQL Server) de Business Server à la topologie et de publier la topologie.  <br/> |Pour définir une topologie afin qu’elle intègre des bases de données d’archivage, un compte membre du groupe Utilisateurs local est requis.  <br/> Pour publier la topologie, un compte qui est membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins et qui possède des autorisations de contrôle total (en lecture/écriture/modification) sur le partage de fichiers à utiliser pour le Skype pour stockage de fichiers de serveur d’entreprise (afin que topologie Générateur peut configurer les listes DACL requis).  <br/> |[Ajouter des bases de données d’archivage à un déploiement existant dans Skype pour Business Server 2015](add-archiving-databases.md) <br/> |
|**Configurer l’authentification de serveur à serveur (uniquement si vous utilisez l’intégration de Microsoft Exchange)** <br/> |Configurez les serveurs pour activer l’authentification entre Skype pour Business Server et Exchange. Nous vous recommandons d’exécution **Test-CsExchangeStorageConnectivity testuser_sipUri-benne du dossier** pour valider l’archivage de connectivité de stockage avant d’activer l’archivage de Exchange. <br/> |Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.  <br/> |Gérer l’authentification de serveur à serveur  <br/> |
|**Configurer les stratégies et les options d’archivage** <br/> |Configurer l’archivage, y compris si vous souhaitez utiliser l’intégration de Microsoft Exchange, la stratégie globale et les stratégies de site et de l’utilisateur (lorsque ne pas intégration de Microsoft Exchange pour le stockage des données) et archivage des options, telles que le mode critique et des données exportation et le nettoyage.  <br/> Si l’intégration de Microsoft Exchange, configurer les stratégies de contenir de Exchange Place selon le cas.  <br/> |Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.  <br/> |[Configurer les options d’archivage de Skype pour Business Server 2015](configure-archiving-options.md) <br/> Échange de documentation du produit (si l’intégration de Microsoft Exchange).  <br/> |
   


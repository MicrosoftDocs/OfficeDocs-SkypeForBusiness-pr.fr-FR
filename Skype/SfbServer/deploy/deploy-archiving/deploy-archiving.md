---
title: Déployer l’archivage pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Résumé : Lisez cette rubrique pour découvrir comment déployer l’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: e9351ed9b13b2e3bbc416f9ff3e1141c2de01a08
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758186"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Déployer l’archivage pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment déployer l’archivage pour Skype Entreprise Server.
  
L’archivage est installé automatiquement sur chaque serveur frontal de votre déploiement Skype Entreprise Server, mais vous devez toujours effectuer les étapes de configuration et de configuration initiales avant de pouvoir l’utiliser. Avant de commencer, assurez-vous que vous êtes familiarisé avec les concepts de [plan d’archivage dans Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Liste de vérification du déploiement

La façon dont vous définissez l’archivage dépend de l’option de stockage que vous choisissez : 
  
- Si vous utilisez l’intégration Exchange Microsoft pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer Skype Entreprise Server stratégies d’archivage pour vos utilisateurs. Au lieu de cela, vous configurez les stratégies de Exchange In-Place pour prendre en charge l’archivage pour les utilisateurs Exchange, avec leurs boîtes aux lettres mises en In-Place archive. Pour plus d’informations sur la configuration de ces stratégies, voir la documentation Exchange produit.
    
- Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez ajouter des bases de données d’archivage Skype Entreprise Server (bases de données SQL Server) à votre topologie, publier la topologie mise à jour, puis configurer les stratégies et paramètres d’archivage pour vos utilisateurs. Vous pouvez déployer des bases de données d’archivage en même temps que votre topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Édition Standard. Ce document décrit comment déployer des bases de données d’archivage en les ajoutant à un déploiement existant.
    
Si vous activez l’archivage sur un pool frontal ou un serveur Édition Standard, vous devez l’activer pour tous les autres pools frontux et serveurs Édition Standard dans votre déploiement. Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée. Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.
  
> [!IMPORTANT]
> Si l’archivage est essentiel dans votre organisation pour des raisons de conformité, veillez à déployer l’archivage, à configurer des stratégies et d’autres options au niveau approprié, puis à activer l’archivage pour tous les utilisateurs appropriés avant d’activer ces utilisateurs pour Skype Entreprise Server. 
  
Le tableau suivant décrit les étapes nécessaires pour déployer l’archivage dans une topologie existante.
  
|**Étape**|**Étapes**|**Rôles et appartenance aux groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> |Pour utiliser l’intégration microsoft Exchange (en utilisant Exchange pour le stockage d’archivage pour tout ou partie des utilisateurs), vous avez besoin d’un déploiement Exchange existant.  <br/> Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour le stockage d’archivage pour tout ou partie des utilisateurs, SQL Server sur le serveur qui stockera les données d’archivage.  <br/> L’archivage s’exécute sur les serveurs frontux d’un pool Enterprise et Édition Standard serveurs. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |[Server requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Exigences environnementales pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Planifier l’intégration de Skype Entreprise et d’Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[System requirements for Skype Entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Créez la topologie interne appropriée pour prendre en charge l’archivage (uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement)** <br/> |Exécutez le Générateur de topologie pour ajouter Skype Entreprise Server bases de données d’archivage (SQL Server bases de données) à la topologie, puis publiez la topologie.  <br/> |Pour définir une topologie pour incorporer des bases de données d’archivage, un compte membre du groupe d’utilisateurs local.  <br/> Pour publier la topologie, un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers Skype Entreprise Server (afin que le Générateur de topologie puisse configurer les DAC requises).  <br/> |[Ajouter des bases de données d’archivage à un déploiement existant dans Skype Entreprise Server](add-archiving-databases.md) <br/> |
|**Configurer l’authentification de serveur à serveur (uniquement en cas d’utilisation de Microsoft Exchange’intégration)** <br/> |Configurez les serveurs pour activer l’authentification entre Skype Entreprise Server et Exchange. Nous vous recommandons d’exécutez **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster** pour valider la connectivité Exchange stockage d’archivage avant d’activer l’archivage. <br/> |Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.  <br/> |Gérer l’authentification de serveur à serveur  <br/> |
|**Configurer les options et stratégies d’archivage** <br/> |Configurez l’archivage, notamment s’il faut utiliser l’intégration Microsoft Exchange, la stratégie globale et les stratégies de site et d’utilisateur (lorsque vous n’utilisez pas l’intégration de Microsoft Exchange pour tout le stockage de données), ainsi que des options d’archivage spécifiques, telles que le mode critique et l’exportation et la purge des données.  <br/> Si vous utilisez l’intégration Exchange Microsoft, configurez les stratégies de Exchange In-Place en attente, le cas échéant.  <br/> |Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.  <br/> |[Configurer les options d’archivage pour Skype Entreprise Server](configure-archiving-options.md) <br/> Exchange documentation produit (si vous utilisez Microsoft Exchange’intégration).  <br/> |
   


---
title: Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: d4609d557e5c55b680c4c0761f24cc4f320afcbd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095108"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015.
  
Le serveur de conversation permanente peut être installé avec Skype Entreprise Server 2015 Enterprise Edition ou Standard Edition. Les conditions requises dépendent de l’édition de Skype Entreprise Server 2015 que vous avez installée et des exigences de performances de votre entreprise. Enterprise Edition peut prendre en charge jusqu’à 80 000 utilisateurs simultanés ; Standard Edition peut prendre en charge jusqu’à 20 000 utilisateurs simultanés. La conversation permanente se compose d’un composant frontal, ainsi que d’un composant de base de SQL principal.
  
Avant de déployer le serveur de conversation permanente, vous devez vous assurer que la configuration matérielle et logicielle suivante est respectée :
  
- Matériel qui répond à la configuration minimale requise pour prendre en charge Skype Entreprise Server 2015, le serveur de conversation permanente, les serveurs de bases de données et les serveurs de fichiers. Pour plus d’informations, [voir Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Système d’exploitation et logiciels de base de données pris en charge.
    
    Pour plus d’informations sur les systèmes d’exploitation et les logiciels de base de données pris en charge, ainsi que sur les conditions requises pour la mise à jour de Windows, voir [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Serveur frontal Skype Entreprise Server 2015. Le serveur frontal est la base du routage SIP (Session Initiation Protocol), ce qui rend possible la communication entre les ordinateurs exécutant le serveur de conversation permanente et la fonctionnalité de conversation permanente. 
    
- Logiciel Message Queuing. Utilisé par le serveur de conversation permanente et le service de conformité de conversation permanente, s’il est déployé.
    
Les sections suivantes décrivent les exigences spécifiques pour le serveur de conversation permanente et la base de données qui stocke les données de conversation permanente.

> [!NOTE] 
> La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. Les mêmes fonctionnalités sont disponibles dans Teams. Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015. 
  
## <a name="front-end-server-requirements"></a>Conditions requises pour le serveur frontal

Les conditions requises pour le serveur frontal varient selon que vous déployez un serveur de conversation permanente avec Skype Entreprise Server 2015 Enterprise Edition ou Standard Edition.
  
- Si vous déployez un serveur de conversation permanente avec Skype Entreprise Server 2015 Enterprise Edition, vous pouvez déployer le serveur frontal de conversation permanente sur un ou plusieurs ordinateurs autonomes dans le pool Enterprise Edition. Vous ne pouvez pas cocérer les serveurs frontux de conversation permanente sur le serveur frontal Skype Entreprise Server 2015. 
    
    Un serveur frontal de conversation permanente unique peut prendre en charge 20 000 utilisateurs actifs. Vous pouvez avoir un pool de serveurs de conversation permanente avec jusqu’à 4 serveurs frontaux actifs, ce qui prend en charge un total de 80 000 utilisateurs simultanés. 
    
- Si vous déployez un serveur de conversation permanente avec Skype Entreprise Server 2015 Standard Edition, vous pouvez célérer la conversation permanente avec le serveur frontal. Ce déploiement à serveur unique peut prendre en charge jusqu’à 20 000 utilisateurs. 
    
## <a name="persistent-chat-server-database-requirements"></a>Conditions requises pour la base de données du serveur de conversation permanente

Le serveur de conversation permanente nécessite SQL Server base de données pour stocker l’historique et le contenu de la salle de conversation, les données de configuration, les données de mise en service des utilisateurs et d’autres métadonnées pertinentes. Éventuellement, il utilise la base de données de conformité de conversation permanente pour stocker les données de conformité. Les bases de données de conversation permanente peuvent être coclaquées sur la même SQL Server, ou même la même instance SQL de conversation permanente, que les bases de données principale. 
  
- Si vous installez le serveur de conversation permanente avec Skype Entreprise Server 2015 Enterprise Edition, pour garantir des performances optimales, il est recommandé d’installer le magasin de fichiers de conversation permanente.
    
- Si vous installez le serveur de conversation permanente avec Skype Entreprise Server 2015 Standard Edition, vous pouvez déployer le serveur principal du magasin de conversation permanente sur l’instance SQL Server Express locale.
    
- La base de données de conversation permanente (mgc) et la base de données de conformité (mgccomp) peuvent se trouver dans la même instance de SQL Server ou sur des serveurs SQL différents.
    
Pour préparer une plateforme de serveur de base de données, assurez-vous que chaque ordinateur répond à la configuration matérielle requise, puis installez le logiciel prérequis. La plateforme serveur pour les serveurs de base de données de conversation permanente nécessite le même matériel que le serveur de base de données principal Skype Entreprise Server 2015. Pour plus d’informations, [voir Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Sur le serveur de base de données, assurez-vous que l’une des applications logicielles suivantes est installée :

- Microsoft SQL Server 2017 avec le dernier Service Pack.

- Microsoft SQL Server 2016 avec Le Service Pack 1 et vous devez exécuter avec la mise à jour cumulative 7 de Skype Entreprise Server ou les mises à jour ultérieures. Nous vous recommandons d’SQL Server 2016 avec le dernier Service Pack. Pour plus d’informations sur l’installation Microsoft SQL Server 2016, voir [Install SQL Server 2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 et vous devez exécuter avec la mise à jour cumulative 6 ou ultérieure de Skype Entreprise Server. Nous vous recommandons d’SQL Server 2014 avec le dernier Service Pack. Pour plus d’informations sur l’installation Microsoft SQL Server 2014, voir [Install SQL Server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack. Pour plus d’informations sur l’installation Microsoft SQL Server 2012, voir [Install SQL Server 2012](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110)).

## <a name="persistent-chat-server-certificate-requirements"></a>Conditions requises pour les certificats du serveur de conversation permanente

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [Deploy Skype for Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur la configuration matérielle et logicielle requise, consultez les rubriques suivantes :
  
- [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Exigences environnementales pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)

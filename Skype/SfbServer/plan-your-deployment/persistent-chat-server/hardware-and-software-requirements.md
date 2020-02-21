---
title: Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Résumé : consultez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype entreprise Server 2015.'
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213230"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype entreprise Server 2015
 
**Résumé :** Consultez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype entreprise Server 2015.
  
Le serveur de conversation permanente peut être installé avec Skype entreprise Server 2015 Enterprise Edition ou Standard Edition. La configuration requise dépend de l’édition de Skype entreprise Server 2015 que vous avez installée, ainsi que des exigences de votre entreprise en matière de performances. Enterprise Edition peut prendre en charge jusqu’à 80 000 utilisateurs simultanés ; Standard Edition peut prendre en charge jusqu’à 20 000 utilisateurs simultanés. La conversation permanente se compose d’un composant frontal et d’un composant de base de données SQL principal.
  
Avant de déployer le serveur de conversation permanente, vous devez vous assurer que la configuration matérielle et logicielle requise suivante est satisfaite :
  
- Matériel conforme à la configuration minimale requise pour la prise en charge de Skype entreprise Server 2015, du serveur de conversation permanente, des serveurs de bases de données et des serveurs de fichiers. Pour plus d’informations, reportez-vous à la rubrique [Server Requirements for Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Logiciels de base de données et de système d’exploitation pris en charge.
    
    Pour plus d’informations sur les systèmes d’exploitation et les logiciels de base de données pris en charge, ainsi que sur la configuration requise pour Windows Update, voir [Server Requirements for Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Serveur frontal Skype entreprise Server 2015. Le serveur frontal est la base du routage SIP (Session Initiation Protocol), qui rend possible la communication entre les ordinateurs exécutant le serveur de conversation permanente et la fonctionnalité de conversation permanente. 
    
- Logiciel Message Queuing. Utilisé par le serveur de conversation permanente et le service de conformité de conversation permanente, s’il est déployé.
    
Les sections suivantes décrivent les conditions requises spécifiques pour le serveur de conversation permanente et la base de données qui stocke les données de conversation permanente.

> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les mêmes fonctionnalités sont disponibles dans Teams. Pour plus d’informations, consultez [la rubrique prise en main de la mise à niveau de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous devez utiliser la conversation permanente, vos choix sont de migrer les utilisateurs qui ont besoin de cette fonctionnalité vers teams ou de continuer à utiliser Skype entreprise Server 2015. 
  
## <a name="front-end-server-requirements"></a>Configuration requise pour le serveur frontal

Les exigences de serveur frontal varient selon que vous déployez un serveur de conversation permanente avec Skype entreprise Server 2015 Enterprise Edition ou Standard Edition.
  
- Si vous déployez le serveur de conversation permanente avec Skype entreprise Server 2015 Enterprise Edition, vous pouvez déployer le serveur frontal de serveur de conversation permanente sur un ou plusieurs ordinateurs autonomes dans le pool Enterprise Edition. Vous ne pouvez pas colocaliser les serveurs frontaux de conversation permanente sur le serveur frontal Skype entreprise Server 2015. 
    
    Un seul serveur frontal de serveur de conversation permanente peut prendre en charge 20 000 utilisateurs actifs. Vous pouvez disposer d’un pool de serveurs de conversation permanente avec jusqu’à 4 serveurs frontaux actifs, ce qui prend en charge un total de 80 000 utilisateurs simultanés. 
    
- Si vous déployez le serveur de conversation permanente avec Skype entreprise Server 2015 Standard Edition, vous pouvez colocaliser la conversation permanente avec le serveur frontal. Ce déploiement sur un seul serveur peut prendre en charge jusqu’à 20 000 utilisateurs. 
    
## <a name="persistent-chat-server-database-requirements"></a>Configuration requise pour la base de données de serveur de conversation permanente

Le serveur de conversation permanente nécessite le logiciel de base de données SQL Server pour stocker l’historique et le contenu de la salle de conversation, les données de configuration, les données de mise en service des utilisateurs et d’autres métadonnées pertinentes. Il utilise éventuellement la base de données de conformité de la conversation permanente pour stocker les données de conformité. Les bases de données de conversation permanente peuvent être colocalisées sur le même serveur SQL Server, voire sur la même instance SQL que les bases de données principales. 
  
- Si vous installez le serveur de conversation permanente avec Skype entreprise Server 2015 Enterprise Edition afin de garantir des performances optimales, il est recommandé d’installer le magasin de fichiers de conversation permanente.
    
- Si vous installez le serveur de conversation permanente avec Skype entreprise Server 2015 Standard Edition, vous pouvez déployer le serveur principal du magasin de conversation permanente sur l’instance SQL Server Express locale.
    
- La base de données de conversation permanente (MGC) et la base de données de conformité (mgccomp) peuvent se trouver dans la même instance de SQL Server ou sur des serveurs SQL différents.
    
Pour préparer une plateforme de serveur de base de données, assurez-vous que chaque ordinateur répond à la configuration matérielle requise, puis installez les logiciels prérequis. La plateforme de serveur pour les serveurs de bases de données de conversation permanente nécessite le même matériel que le serveur de base de données principal Skype entreprise Server 2015. Pour plus d’informations, reportez-vous à la rubrique [Server Requirements for Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Sur le serveur de base de données, assurez-vous que l’une des applications logicielles suivantes est installée :

- Microsoft SQL Server 2017 avec le Service Pack le plus récent.

- Microsoft SQL Server 2016 avec le Service Pack 1 et vous devez l’exécuter avec la mise à jour cumulative 7 ou les versions ultérieures de Skype entreprise Server. Nous vous recommandons d’exécuter SQL Server 2016 avec le dernier Service Pack. Pour plus d’informations sur l’installation de Microsoft SQL Server 2016, voir [install SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 et vous devez l’exécuter avec la mise à jour cumulative 6 ou versions ultérieures de Skype entreprise Server. Nous vous recommandons d’exécuter SQL Server 2014 avec le dernier Service Pack. Pour plus d’informations sur l’installation de Microsoft SQL Server 2014, voir [install SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (édition 64 bits) et nous vous recommandons de l’exécuter avec le dernier Service Pack. Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, voir [install SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Conditions requises pour les certificats de serveur de conversation permanente

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [Deploy Skype for Business server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Pour plus d'informations

Pour plus d’informations sur la configuration matérielle et logicielle requise, consultez les rubriques suivantes :
  
- [Configuration requise pour le serveur pour Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Configuration environnementale requise pour Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    


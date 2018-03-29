---
title: Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les exigences matérielles et logicielles de serveur Chat persistant dans Skype pour Business Server 2015.'
ms.openlocfilehash: a56f939360edae0da47198e4a3810f70712b6ab8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les exigences matérielles et logicielles de serveur Chat persistant dans Skype pour Business Server 2015.
  
Serveur de conversation permanent peut être installé avec Skype pour Business Server 2015 Enterprise Edition ou Standard Edition. Configuration requise dépend de la version de Skype pour 2015 de serveur d’entreprise que vous avez installé et les exigences de performances de votre entreprise. La version Enterprise Edition peut prendre en charge jusqu’à 80 000 utilisateurs simultanés tandis que la version Standard Edition peut en prendre en charge jusqu’à 20 000. La conversation permanente comporte un composant frontal ainsi qu’un composant de base de données SQL principal.
  
Avant de déployer persistant Chat Server, vous devez vous assurer que les exigences matérielles et logicielles suivantes sont remplies :
  
- Matériel qui répond à la configuration minimale requise pour la prise en charge de Skype pour Business Server 2015, persistant Chat Server, les serveurs de base de données et serveurs de fichiers. Pour plus d’informations, consultez [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Système d’exploitation et logiciels de base de données pris en charge.
    
    Pour plus d’informations sur les systèmes d’exploitation pris en charge et les logiciels de base de données et Windows mise à jour de la configuration requise, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype pour Business Server 2015 Front-End Server. Le serveur frontal est la Fondation de protocole SIP (Session Initiation) routage, qui permet la communication entre des ordinateurs exécutant persistant Chat Server et la fonctionnalité de conversation permanent. 
    
- Logiciel Message Queuing. Utilisé par le service serveur de Chat persistant et conformité de conversation permanent, si déployé.
    
Les sections suivantes décrivent les exigences spécifiques pour persistant Chat Server et la base de données qui stocke les données de Chat persistant.
  
## <a name="front-end-server-requirements"></a>Configuration requise pour le serveur frontal

Exigences de serveur principal avant dépendant de si vous déployez serveur Chat persistant avec Skype pour Business Server 2015 Enterprise Edition ou Standard Edition.
  
- Si vous déployez un serveur Chat persistant avec Skype pour Business Server 2015 Enterprise Edition, vous pouvez déployer le persistant Chat Server serveur frontal sur un ou plusieurs ordinateurs autonomes dans le pool Enterprise Edition. Vous ne pouvez pas colocaliser les persistant Chat serveurs frontaux sur le Skype pour Business Server 2015 serveur frontal. 
    
    Un seul persistant Chat Server serveur frontal peut prendre en charge les 20 000 utilisateurs actifs. Vous pouvez avoir un pool de serveurs de conversation permanent avec jusqu'à 4 ports front-end active ainsi prise en charge d’un total de 80 000 utilisateurs simultanés. 
    
- Si vous déployez un serveur Chat persistant avec Skype pour 2015 Business Server Standard Edition, vous pouvez colocaliser Chat permanente avec le serveur frontal. Ce déploiement à serveur unique peut prendre en charge jusqu’à 20 000 utilisateurs. 
    
## <a name="persistent-chat-server-database-requirements"></a>Exigences de base de données serveur Chat persistants

Serveur de conversation persistant nécessite un logiciel de base de données SQL Server pour stocker l’historique de la salle de conversation et de contenu, les données de configuration, les données de configuration utilisateur et autres métadonnées pertinentes. Le cas échéant, il utilise la base de données de conformité de conversation permanent pour stocker des données de conformité. Il est possible de colocaliser les bases de données de conversation permanente sur le même serveur SQL Server, voire même la même instance SQL, que les bases de données principales. 
  
- Si vous installez serveur de Chat persistant avec Skype pour Business Server 2015 Enterprise Edition, pour assurer des performances optimales, il est recommandé que vous installez le magasin de fichiers Chat persistant.
    
- Si vous installez un serveur de Chat persistant avec Skype 2015 Business Server Standard Edition, vous pouvez déployer le persistant Chat banque serveur principal sur l’instance de SQL Server Express locale.
    
- La base de données Chat persistant (mgc) et la base de données de conformité (mgccomp) peuvent se trouver dans la même instance de SQL Server ou sur différents serveurs SQL.
    
Pour préparer une plateforme de serveur de base de données, vérifiez que chaque ordinateur respecte la configuration matérielle requise, puis installez les logiciels prérequis. La plate-forme de serveur pour les serveurs de base de données de Chat permanente nécessite le même matériel que le Skype pour le serveur de base de données back-end Business Server 2015. Pour plus d’informations, consultez [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Sur le serveur de bases de données, vérifiez que l’une des applications logicielles suivantes est installée :
  
- Microsoft SQL Server 2012. Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, consultez [installation de SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).
    
- R2 2008 de Microsoft SQL Server. Pour plus d’informations sur l’installation de Microsoft SQL Server 2008 R2, consultez [Installation de SQL Server (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702).
    
## <a name="persistent-chat-server-certificate-requirements"></a>Configuration requise des certificats serveur Chat persistant

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de banques de fichiers, voir [Déploiement de Skype pour Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur la configuration matérielle et logicielle, voir les rubriques suivantes :
  
- [Configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Besoins environnementaux dans Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    


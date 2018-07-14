---
title: Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 4daf53219937a4ffcfee0e51d80cffb7f1626cf5
ms.sourcegitcommit: 11adc15c5191d7bf6bb37058cae3d54649c25e97
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2018
ms.locfileid: "20363929"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype pour Business Server 2015.
  
Serveur de conversation permanente peut être installé avec Skype pour Business Server 2015 Enterprise Edition ou Standard Edition. Exigences dépendent de l’édition de Skype pour Business Server 2015 que vous avez installé et les exigences de performances de votre entreprise. La version Enterprise Edition peut prendre en charge jusqu’à 80 000 utilisateurs simultanés tandis que la version Standard Edition peut en prendre en charge jusqu’à 20 000. La conversation permanente comporte un composant frontal ainsi qu’un composant de base de données SQL principal.
  
Avant de déployer le serveur de conversation permanente, vous devez vous assurer que les conditions matérielles et logicielles suivantes sont remplies :
  
- Matériel conforme à la configuration minimale requise pour prendre en charge Skype pour Business Server 2015, Persistent Chat Server, les serveurs de base de données et les serveurs de fichiers. Pour plus d’informations, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Système d’exploitation et logiciels de base de données pris en charge.
    
    Pour plus d’informations sur les systèmes d’exploitation pris en charge et les logiciels de base de données et Windows mise à jour de la configuration requise, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Skype pour Business Server 2015 Front-End Server. Le serveur frontal est la base de protocole SIP (Session Initiation) routage, qui permet la communication entre les ordinateurs exécutant le serveur de conversation permanente et la fonctionnalité de conversation permanente. 
    
- Logiciel Message Queuing. Utilisé par le service serveur de conversation permanente et de conformité de conversation permanente, s’il est déployé.
    
Les sections suivantes décrivent la configuration requise pour le serveur de conversation permanente et la base de données qui stocke les données de conversation permanente.
  
## <a name="front-end-server-requirements"></a>Configuration requise pour le serveur frontal

Configuration requise de serveur frontal dépend si vous déployez des serveurs de conversation permanente avec Skype pour Business Server 2015 Enterprise Edition ou Standard Edition.
  
- Si vous déployez un serveur de conversation permanente avec Skype pour Business Server 2015 Enterprise Edition, vous pouvez déployer le Persistent Chat Server serveur frontal sur un ou plusieurs ordinateurs autonomes dans le pool Enterprise Edition. Vous ne pouvez pas colocaliser Persistent Chat serveurs frontaux sur le Skype pour Business Server 2015 serveur frontal. 
    
    Un seul Persistent Chat Server serveur frontal peut prendre en charge les 20 000 utilisateurs actifs. Vous pouvez avoir un pool de serveurs de conversation permanente avec jusqu'à 4 serveurs frontaux active ainsi prenant en charge un total de 80 000 utilisateurs simultanés. 
    
- Si vous déployez un serveur de conversation permanente avec Skype pour 2015 Business Server Standard Edition, vous pouvez colocaliser conversation permanente avec le serveur frontal. Ce déploiement à serveur unique peut prendre en charge jusqu’à 20 000 utilisateurs. 
    
## <a name="persistent-chat-server-database-requirements"></a>Exigences de base de données de serveur de conversation permanentes

Persistent Chat Server requiert le logiciel de base de données SQL Server pour stocker l’historique de la salle de conversation et contenu, les données de configuration, données de configuration utilisateur et autres métadonnées appropriées. Si vous le souhaitez, il utilise la base de données de conformité de conversation permanente pour stocker les données de conformité. Il est possible de colocaliser les bases de données de conversation permanente sur le même serveur SQL Server, voire même la même instance SQL, que les bases de données principales. 
  
- Si vous installez le serveur de conversation permanente avec Skype pour Business Server 2015 Enterprise Edition, pour garantir des performances optimales, il est recommandé que vous installez le magasin de fichiers de conversation permanente.
    
- Si vous installez le serveur de conversation permanente avec Skype pour 2015 Business Server Standard edition, vous pouvez déployer le Persistent Chat magasin de serveur principal sur l’instance SQL Server Express locale.
    
- La base de données conversation permanente (mgc) et la base de données de conformité (mgccomp) peuvent se trouver dans la même instance de SQL Server ou sur différents serveurs SQL.
    
Pour préparer une plateforme de serveur de base de données, vérifiez que chaque ordinateur respecte la configuration matérielle requise, puis installez les logiciels prérequis. La plate-forme de serveur pour les serveurs de base de données de conversation permanente requiert le même matériel que le Skype pour le serveur de base de données principale Business Server 2015. Pour plus d’informations, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Sur le serveur de bases de données, vérifiez que l’une des applications logicielles suivantes est installée :

- Microsoft SQL Server 2014 et que vous devez exécuter avec Skype pour Business Server mise à jour Cumulative 6 ou versions ultérieures. Nous vous recommandons d’exécuter SQL Server 2014 avec le service pack le plus récent. Pour plus d’informations sur l’installation de Microsoft SQL Server 2014, consultez [installer SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (Édition 64 bits) et nous recommandé en cours d’exécution avec le service pack le plus récent. Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, consultez [installer SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

- Microsoft SQL Server 2008 R2 (Édition 64 bits) et nous recommandé en cours d’exécution avec le service pack le plus récent. Pour plus d’informations sur l’installation de Microsoft SQL Server 2008 R2, consultez [Installation de SQL Server (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702). 
    
## <a name="persistent-chat-server-certificate-requirements"></a>Configuration requise des certificats serveur de conversation permanente

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [Déployer de Skype pour Business Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur la configuration matérielle et logicielle, voir les rubriques suivantes :
  
- [Configuration serveur requise pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Conditions préalables d’environnement pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    


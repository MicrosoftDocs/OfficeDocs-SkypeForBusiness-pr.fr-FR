---
title: Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 'Résumé: Lisez cette rubrique pour en savoir plus sur la configuration matérielle et logicielle requise pour le serveur Chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 8dfd21426cee6b32e6f06c35297ccd5fd8dc534e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297098"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Pour en savoir plus sur les configurations matérielles et logicielles requises pour le serveur Chat permanent dans Skype entreprise Server 2015, consultez cette rubrique.
  
Le serveur de chat permanent peut être installé avec Skype entreprise Server 2015 Enterprise Edition ou Standard Edition. Les exigences varient en fonction de la version de Skype entreprise Server 2015 que vous avez installée et des exigences en termes de performances de votre entreprise. La version Enterprise Edition peut prendre en charge jusqu’à 80 000 utilisateurs simultanés tandis que la version Standard Edition peut en prendre en charge jusqu’à 20 000. La conversation permanente comporte un composant frontal ainsi qu’un composant de base de données SQL principal.
  
Avant de déployer le serveur de chat permanent, vous devez vous assurer que les configurations matérielles et logicielles suivantes sont respectées:
  
- Matériel qui répond à la configuration minimale requise pour la prise en charge de Skype entreprise Server 2015, serveur de discussions permanent, serveurs de base de données et serveurs de fichiers. Pour plus d’informations, reportez-vous [à configuration requise pour Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Système d’exploitation et logiciels de base de données pris en charge.
    
    Pour plus d’informations sur les systèmes d’exploitation pris en charge et les logiciels de base de données et sur Windows Update requise, voir [Configuration requise pour Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- Serveur frontal Skype entreprise Server 2015. Le serveur frontal est le serveur principal pour le routage SIP (Session Initiation Protocol), qui permet de communiquer entre les ordinateurs exécutant le serveur Chat permanent et la fonctionnalité de conversation permanente possible. 
    
- Logiciel Message Queuing. Utilisé par le serveur de chat permanent et le service de conformité des conversations permanentes, s’il est déployé.
    
Les sections suivantes décrivent les conditions requises pour le serveur de chat permanent et la base de données qui stocke les données de chat permanent.

> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
  
## <a name="front-end-server-requirements"></a>Configuration requise pour le serveur frontal

Les exigences en matière de serveur frontal varient selon que vous déployez un serveur Chat permanent avec Skype entreprise Server 2015 Enterprise Edition ou Standard Edition.
  
- Si vous déployez le serveur de chat permanent avec Skype entreprise Server 2015 Enterprise Edition, vous pouvez déployer le serveur frontal de chat permanent sur un ou plusieurs ordinateurs autonomes du pool Enterprise Edition. Vous ne pouvez pas collocater les serveurs front-end chat permanents du serveur frontal Skype entreprise Server 2015. 
    
    Un seul serveur frontal de chat permanent peut prendre en charge des utilisateurs actifs de 20 000. Vous pouvez disposer d’un pool de serveurs de chat permanent avec un maximum de 4 points de terminaison actifs prenant en charge le nombre total d’utilisateurs concurrents 80 000. 
    
- Si vous déployez le serveur de chat permanent avec Skype entreprise Server 2015 Standard Edition, vous pouvez collocate des conversations permanentes avec le serveur frontal. Ce déploiement à serveur unique peut prendre en charge jusqu’à 20 000 utilisateurs. 
    
## <a name="persistent-chat-server-database-requirements"></a>Exigences de base de données serveur de chat permanent

Le serveur Chat permanent nécessite le logiciel de base de données SQL Server pour stocker l’historique des salles de conversation et le contenu, les données de configuration, les données de mise en service des utilisateurs et d’autres métadonnées pertinentes. Le cas échéant, elle utilise la base de données de conformité des conversations permanentes pour stocker les données de conformité. Il est possible de colocaliser les bases de données de conversation permanente sur le même serveur SQL Server, voire même la même instance SQL, que les bases de données principales. 
  
- Si vous installez le serveur Chat permanent avec Skype entreprise Server 2015 Enterprise Edition, pour garantir des performances optimales, nous vous recommandons d’installer le magasin de fichiers de chat permanent.
    
- Si vous installez le serveur Chat permanent avec Skype entreprise Server 2015 Standard Edition, vous pouvez déployer le serveur principal de la gestion des conversations persistantes dans l’instance SQL Server Express locale.
    
- La base de données de chat permanent (MGC) et la base de données de conformité (mgccomp) peuvent être localisées dans la même instance de SQL Server ou sur des serveurs SQL Server différents.
    
Pour préparer une plateforme de serveur de base de données, vérifiez que chaque ordinateur respecte la configuration matérielle requise, puis installez les logiciels prérequis. La plateforme serveur pour les serveurs de base de données de chat permanent nécessite le même matériel que le serveur de base de données principale de Skype entreprise Server 2015. Pour plus d’informations, reportez-vous à la rubrique [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Sur le serveur de bases de données, vérifiez que l’une des applications logicielles suivantes est installée :

- Microsoft SQL Server 2017 avec le dernier Service Pack.

- Microsoft SQL Server 2016 avec Service Pack 1 et vous devez l’exécuter avec la mise à jour cumulative 7 ou une version ultérieure de Skype entreprise Server. Nous vous recommandons d’exécuter SQL Server 2016 avec le dernier Service Pack. Pour plus d’informations sur l’installation de Microsoft SQL Server 2016, voir [installer SQL server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).

- Microsoft SQL Server 2014 et vous devez exécuter la mise à jour cumulative 6 ou une version ultérieure de Skype entreprise Server. Nous vous recommandons d’exécuter SQL Server 2014 avec le dernier Service Pack. Pour plus d’informations sur l’installation de Microsoft SQL Server 2014, voir [installer SQL server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).

- Microsoft SQL Server 2012 (64-bit Edition) et nous vous conseillons d’utiliser le dernier Service Pack. Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, voir [installer SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).

## <a name="persistent-chat-server-certificate-requirements"></a>Conditions requises pour le certificat serveur Chat permanent

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [déployer Skype entreprise Server 2015](../../deploy/deploy.md). 
  
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur la configuration matérielle et logicielle, voir les rubriques suivantes :
  
- [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    


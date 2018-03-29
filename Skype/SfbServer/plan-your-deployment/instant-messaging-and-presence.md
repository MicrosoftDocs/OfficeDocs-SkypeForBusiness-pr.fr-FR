---
title: Planifier la messagerie instantanée et la présence dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Résumé : Apprenez à planifier pour la messagerie instantanée et de présence dans Skype Business Server 2015.'
ms.openlocfilehash: 1934f0308cda59b52073c47d1652ad2286bd6977
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>Planifier la messagerie instantanée et la présence dans Skype Entreprise Server 2015
 
**Résumé :** découvrez comment planifier la messagerie instantanée et la présence dans Skype Entreprise Server 2015.
  
Planifier la messagerie instantanée et la présence dans Skype Entreprise Server 2015. Pour en savoir plus sur les options de déploiement spécifiques, telles que l’activation ou désactivation hors connexion messagerie instantanée (IM), reportez-vous à la section [déploiement de messagerie instantanée et de présence dans Skype pour Business Server 2015](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>Planifier la messagerie instantanée et la présence dans Skype Entreprise Server 2015

Avant serveurs fournissent des fonctionnalités du serveur de l’entreprise telles que la messagerie instantanée (IM) et présence de base Skype et sont inclus dans chaque Skype pour le déploiement du serveur de l’entreprise. Il existe deux éditions : Skype pour Business Server Enterprise Edition, qui est principalement conçu pour les grandes entreprises, et Skype pour Business Server Standard Edition, qui est principalement conçu pour les organisations de petite taille qui souhaitez un petit investissement en matériel et ne nécessitent pas d’options de complète de haute disponibilité. Les deux éditions prennent en charge Skype tous les charges de travail de serveur d’entreprise, y compris la messagerie instantanée, présence, de conférence et de Voix Entreprise.
  
La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. Un participant à une conversation de messagerie instantanée peut ajouter un troisième participant à la conversation à tout moment. Lorsque cela arrive, la fenêtre Conversation change pour prendre en charge des fonctionnalités de conférence.
  
La présence fournit aux utilisateurs des informations sur l’état de présence des autres utilisateurs sur le réseau. Le statut de présence d’un utilisateur fournit des informations pour aider les autres à décider si leur est conseillé de contacter l’utilisateur et s’il faut utiliser des instantanés de messagerie, téléphone ou courrier électronique. La présence permet une communication instantanée lorsque cela est possible, mais fournit aussi des informations indiquant si un utilisateur est en réunion ou hors du bureau, indiquant que la communication instantanée n’est pas possible. L’état de présence est indiqué sous la forme d’une icône dans Skype Entreprise et d’autres applications de présence, notamment le client de messagerie et de collaboration Microsoft Outlook et les logiciels Microsoft SharePoint et Microsoft Office. L’icône de présence représente la disponibilité actuelle et l’envie de communiquer l’utilisateur. 
  
### <a name="technical-requirements"></a>Configuration technique requise

La messagerie instantanée et la présence s’exécutent en permanence sur les pools des serveurs frontaux Enterprise Edition et Standard Edition. Pour plus d’informations sur le matériel pris en charge, les systèmes d’exploitation et les logiciels de base de données, voir [Infrastructure de Skype pour les entreprises](https://technet.microsoft.com/en-us/office/dn947483) et les [exigences pour votre Skype pour environnement d’entreprise](requirements-for-your-environment/requirements-for-your-environment.md).
  
### <a name="enabling-communication-with-external-users"></a>Activation des communications avec les utilisateurs externes

Vous tirerez beaucoup plus profit de votre investissement dans Skype Entreprise Server en permettant à vos utilisateurs de communiquer avec des utilisateurs externes. Exemples d’utilisateurs externes :
  
- Les utilisateurs distants : les utilisateurs de l’organisation, lorsqu’ils travaillent à l’extérieur de votre pare-feu et de périphériques serveur d’entreprise utilisent leurs ordinateurs portables ou autre Skype.
    
- Les utilisateur fédérés : les utilisateurs de sociétés vous travaillez également exécutent Skype pour Business Server. Pour autoriser vos utilisateurs à communiquer facilement avec ces utilisateurs externes, créez des relations fédérées avec ces entreprises. 
    
- Utilisateurs Skype : Les utilisateurs Skype Entreprise peuvent entrer en contact avec des centaines de millions d’utilisateurs Skype à l’aide des fonctionnalités vocales, vidéo et de messagerie instantanée.
    
> [!NOTE]
> AOL, Yahoo et Google Talk ne sont plus pris en charge. 
  
> [!NOTE]
> Pour activer un scénario ou l’ensemble d’entre eux, vous devez déployer un serveur Edge pour renforcer la sécurité des communications entre votre déploiement Skype Entreprise et les utilisateurs externes. Les utilisateurs distants et les utilisateurs d’organisations fédérées de votre organisation seront en mesure de voir la présence des uns et des autres et de communiquer à l’aide de la messagerie instantanée. 
  
> [!NOTE]
> Le protocole XMPP (Extensible Messaging and Presence Protocol) est pris en charge uniquement pour les scénarios de certification JITC (Joint Interoperability Test Command) UCCP (Unified Capabilities Collaboration Platform). 
  
### <a name="archiving-im-content"></a>Archivage du contenu de la messagerie instantanée

Skype Entreprise Server offre des fonctionnalités utiles si votre organisation doit respecter des réglementations en matière de conformité. Vous pouvez utiliser la fonctionnalité d’archivage pour archiver le contenu des messages instantanés soit pour tous les utilisateurs de votre organisation, soit uniquement pour ceux que vous indiquez. Pour plus d’informations, reportez-vous à Planifier l’archivage dans Skype Entreprise Server 2015 dans la documentation de planification. 
  
Si vous avez également déployé Microsoft Exchange Server 2013, vous pouvez intégrer l’archivage des données Exchange avec l’archivage des données Skype Entreprise Server, puis utiliser le même outil pour effectuer des recherches dans ces deux types de données archivées. Pour plus d’informations, consultez Configuration de Skype pour 2015 de serveur d’entreprise utiliser Microsoft Exchange Server 2013 d’archivage.
  
### <a name="topologies-and-components"></a>Topologies et composants

Les seuls composants requis pour la messagerie instantanée (IM) et présence sont les suivants :
  
- Serveurs frontaux de votre organisation (appelés un pool) ou un serveur Standard Edition. Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs. Pour plus d’informations sur les topologies de pool Front-End et de gestion, consultez [avant fin Pool haute disponibilité et gestion](high-availability-and-disaster-recovery/high-availability.md).
    
- Un programme d’équilibrage de la charge, si vous avez un pool frontal Enterprise Edition.
    
### <a name="supported-collocation"></a>Colocalisation prise en charge

La colocalisation est définie comme étant un serveur unique ou un groupe de serveurs avec plusieurs rôles installés. Pour plus d’informations sur la colocalisation, consultez [Notions fondamentales de la topologie pour Skype pour Business Server 2015](topology-basics/topology-basics.md). 
  


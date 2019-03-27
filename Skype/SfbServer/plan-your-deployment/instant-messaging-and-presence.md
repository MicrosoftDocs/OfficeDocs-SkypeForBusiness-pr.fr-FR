---
title: Planification de la messagerie instantanée et présence dans Skype Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Résumé : Découvrez comment planifier pour la messagerie instantanée et présence dans Skype Business Server.'
ms.openlocfilehash: 8d26ad08242248f08e2e54ba7e46d2aa112e362a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898207"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planification de la messagerie instantanée et présence dans Skype Business Server
 
**Résumé :** Découvrez comment planifier pour la messagerie instantanée et présence dans Skype Business Server.
  
Plan pour la messagerie instantanée et présence dans Skype pour Business Server. Pour en savoir plus sur les options de déploiement spécifiques, telles que l’activation ou désactivation hors connexion messagerie instantanée (IM), voir [déployer la messagerie instantanée et présence dans Skype pour Business Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planification de la messagerie instantanée et présence dans Skype Business Server

Serveur frontal fournissent des serveurs frontaux core Skype pour la fonctionnalité Business Server tels que la messagerie instantanée et présence et sont incluses dans chaque Skype pour le déploiement de serveur d’entreprise. Il existe deux éditions : Skype pour Business Server Enterprise Edition, est conçu pour les grandes entreprises, et Skype pour Business Server Standard Edition, qui est conçu principalement pour les petites organisations qui vous souhaitez un plus petit investissement matériel et ne nécessitent pas d’options complète de haute disponibilité. Les deux éditions prennent en charge Skype toutes les charges de travail Business Server, y compris la messagerie instantanée, présence, conférence et voix entreprise.
  
La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. Un participant à une conversation de messagerie instantanée peut ajouter un troisième participant à la conversation à tout moment. Lorsque cela arrive, la fenêtre Conversation change pour prendre en charge des fonctionnalités de conférence.
  
La présence fournit aux utilisateurs des informations sur l’état de présence des autres utilisateurs sur le réseau. Statut de présence d’un utilisateur fournit des informations pour aider les autres à décider s’ils doivent essayer de contacter l’utilisateur et s’il faut utiliser des instantanés de messagerie, le téléphone ou courrier électronique. La présence permet une communication instantanée lorsque cela est possible, mais fournit aussi des informations indiquant si un utilisateur est en réunion ou hors du bureau, indiquant que la communication instantanée n’est pas possible. L’état de présence est indiqué sous la forme d’une icône dans Skype Entreprise et d’autres applications de présence, notamment le client de messagerie et de collaboration Microsoft Outlook et les logiciels Microsoft SharePoint et Microsoft Office. L’icône de présence représente la disponibilité actuelle de l’utilisateur et sa volonté de communiquer. 
  
### <a name="technical-requirements"></a>Configuration technique requise

La messagerie instantanée et la présence s’exécutent en permanence sur les pools des serveurs frontaux Enterprise Edition et Standard Edition. Pour plus d’informations sur le matériel pris en charge, les systèmes d’exploitation et les logiciels de base de données, voir [Passerelles certifié](../../SfbPartnerCertification/certification/infra-gateways.md), [Configuration requise pour votre Skype pour environnement Business 2015](requirements-for-your-environment/requirements-for-your-environment.md)et [Infrastructure requises pour Skype pour Business Server 2019 ](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Activation des communications avec les utilisateurs externes

Vous pouvez augmenter considérablement les avantages de votre investissement dans Skype pour Business Server en activant les utilisateurs à communiquer avec des utilisateurs externes. Exemples d’utilisateurs externes :
  
- Les utilisateurs distants : vos utilisateurs de l’organisation, lorsqu’ils sont trouvent en dehors de vos pare-feu et utilisent leur ordinateur portable ou autres Skype pour les appareils Business Server.
    
- Utilisateurs fédérés : les utilisateurs d’entreprises vous manipulez qui exécutent également Skype pour Business Server. Pour autoriser vos utilisateurs à communiquer facilement avec ces utilisateurs externes, créez des relations fédérées avec ces entreprises. 
    
- Utilisateurs Skype : Les utilisateurs Skype Entreprise peuvent entrer en contact avec des centaines de millions d’utilisateurs Skype à l’aide des fonctionnalités vocales, vidéo et de messagerie instantanée.
    
> [!NOTE]
> AOL, Yahoo et Google Talk ne sont plus pris en charge. 
  
> [!NOTE]
> Pour activer un ou plusieurs de ces scénarios, vous devez déployer un serveur Edge pour vous aider à activer les communications sécurisées entre votre Skype pour le déploiement de serveur d’entreprise et les utilisateurs externes. Les utilisateurs distants de votre organisation et les utilisateurs dans les organisations fédérées sera en mesure de voir la présence de l’autre et communiquer à l’aide de la messagerie instantanée. 
  
> [!NOTE]
> Le protocole XMPP (Extensible Messaging and Presence Protocol) est pris en charge uniquement pour les scénarios de certification JITC (Joint Interoperability Test Command) UCCP (Unified Capabilities Collaboration Platform). 
  
### <a name="archiving-im-content"></a>Archivage du contenu de la messagerie instantanée

Skype pour Business Server fournit des fonctionnalités que vous pouvez utiliser si votre organisation doit respecter les réglementations de conformité. Vous pouvez utiliser la fonctionnalité d’archivage pour archiver le contenu des messages instantanés soit pour tous les utilisateurs de votre organisation, soit uniquement pour ceux que vous indiquez. Pour plus d’informations, voir [planifier l’archivage dans Skype pour Business Server](archiving/archiving.md). 
  
Si vous avez également déployé Microsoft Exchange Server 2013, vous pouvez intégrer l’archivage des données Exchange avec l’archivage des Skype pour les données métiers et utiliser un seul outil pour rechercher les deux types de données archivées. Pour plus d’informations, voir [Configurer les Skype pour Business Server utilisant l’archivage d’Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologies et composants

Les seuls composants requis pour la messagerie instantanée et la présence sont :
  
- Serveurs frontaux de votre organisation (également appelés en tant que pool) ou un serveur Standard Edition server. Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs. Pour plus d’informations sur les topologies de pool frontal et de gestion, voir [un Pool frontal haute disponibilité et gestion](high-availability-and-disaster-recovery/high-availability.md).
    
- Un programme d’équilibrage de la charge, si vous avez un pool frontal Enterprise Edition.
    
### <a name="supported-collocation"></a>Colocalisation prise en charge

La colocalisation est définie comme étant un serveur unique ou un groupe de serveurs avec plusieurs rôles installés. Pour plus d’informations sur la colocalisation, voir [Concepts de topologie pour Skype pour Business Server](topology-basics/topology-basics.md). 
  


---
title: Planifier la messagerie instantanée et la présence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Résumé : Découvrez comment planifier la messagerie instantanée et la présence dans Skype entreprise Server.'
ms.openlocfilehash: d62559afe0c7767ee7863f41b41f2d1b64127643
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815902"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planifier la messagerie instantanée et la présence dans Skype entreprise Server
 
**Résumé :** Découvrez comment planifier la messagerie instantanée et la présence dans Skype entreprise Server.
  
Planifiez la messagerie instantanée et la présence dans Skype entreprise Server. Pour en savoir plus sur les options de déploiement spécifiques, telles que l’activation ou la désactivation de la messagerie instantanée en mode hors connexion, reportez-vous à la rubrique [déploiement de la messagerie instantanée et de la présence dans Skype entreprise Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planifier la messagerie instantanée et la présence dans Skype entreprise Server

Les serveurs frontaux fournissent des fonctionnalités principales de Skype entreprise Server, telles que la messagerie instantanée (mi) et la présence, et qui sont inclus dans chaque déploiement de Skype entreprise Server. Il existe deux éditions disponibles : Skype entreprise Server Enterprise Edition, principalement conçu pour les grandes organisations et Skype entreprise Server Standard Edition, conçu par le biais de petites organisations plus petites. investissement matériel et ne nécessitent pas d’options de haute disponibilité complètes. Les deux éditions prennent en charge toutes les charges de travail de Skype entreprise Server, notamment la messagerie instantanée, la présence, les conférences et l’voix entreprise.
  
La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. Un participant à une conversation de messagerie instantanée peut ajouter un troisième participant à la conversation à tout moment. Lorsque cela arrive, la fenêtre Conversation change pour prendre en charge des fonctionnalités de conférence.
  
La présence fournit aux utilisateurs des informations sur l’état de présence des autres utilisateurs sur le réseau. Le statut de présence d’un utilisateur fournit des informations pour aider les autres à déterminer s’il doit contacter l’utilisateur, et si vous souhaitez utiliser la messagerie instantanée, le téléphone ou le courrier électronique. La présence permet une communication instantanée lorsque cela est possible, mais fournit aussi des informations indiquant si un utilisateur est en réunion ou hors du bureau, indiquant que la communication instantanée n’est pas possible. L’état de présence est indiqué sous la forme d’une icône dans Skype Entreprise et d’autres applications de présence, notamment le client de messagerie et de collaboration Microsoft Outlook et les logiciels Microsoft SharePoint et Microsoft Office. L’icône de présence représente la disponibilité actuelle et la volonté de communication de l’utilisateur. 
  
### <a name="technical-requirements"></a>Configuration technique requise

La messagerie instantanée et la présence s’exécutent en permanence sur les pools des serveurs frontaux Enterprise Edition et Standard Edition. Pour plus d’informations sur les matériels, systèmes d’exploitation et logiciels de base de données compatibles, reportez-vous à la rubrique [passerelles certifiées](../../SfbPartnerCertification/certification/infra-gateways.md), [Configuration requise pour votre environnement Skype entreprise 2015](requirements-for-your-environment/requirements-for-your-environment.md)et [exigences d’Infrastructure pour Skype entreprise Server 2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Activation des communications avec les utilisateurs externes

Vous pouvez considérablement augmenter les avantages de votre investissement dans Skype entreprise Server en permettant aux utilisateurs de communiquer avec des utilisateurs externes. Exemples d’utilisateurs externes :
  
- Utilisateurs distants : les utilisateurs de votre organisation qui travaillent à l’extérieur de votre pare-feu et qui utilisent leur ordinateur portable ou d’autres appareils Skype entreprise Server.
    
- Utilisateurs fédérés : les utilisateurs des entreprises avec lesquelles vous travaillez utilisent également Skype entreprise Server. Pour autoriser vos utilisateurs à communiquer facilement avec ces utilisateurs externes, créez des relations fédérées avec ces entreprises. 
    
- Utilisateurs Skype : Les utilisateurs Skype Entreprise peuvent entrer en contact avec des centaines de millions d’utilisateurs Skype à l’aide des fonctionnalités vocales, vidéo et de messagerie instantanée.
    
> [!NOTE]
> AOL, Yahoo et Google Talk ne sont plus pris en charge. 
  
> [!NOTE]
> Pour pouvoir utiliser l’un ou l’ensemble de ces scénarios, vous devez déployer un serveur Edge pour sécuriser les communications entre le déploiement de Skype entreprise Server et les utilisateurs externes. Les utilisateurs et utilisateurs distants de votre organisation dans les organisations fédérées pourront voir leur présence et communiquer par messagerie instantanée. 
  
> [!NOTE]
> Le protocole XMPP (Extensible Messaging and Presence Protocol) est pris en charge uniquement pour les scénarios de certification JITC (Joint Interoperability Test Command) UCCP (Unified Capabilities Collaboration Platform). 
  
### <a name="archiving-im-content"></a>Archivage du contenu de la messagerie instantanée

Skype entreprise Server fournit des fonctionnalités que vous pouvez utiliser si votre organisation doit respecter les règles de conformité. Vous pouvez utiliser la fonctionnalité d’archivage pour archiver le contenu des messages instantanés soit pour tous les utilisateurs de votre organisation, soit uniquement pour ceux que vous indiquez. Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](archiving/archiving.md). 
  
Si Microsoft Exchange Server 2013 est également déployé, vous pouvez intégrer l’archivage de données Exchange avec l’archivage des données de Skype entreprise Server et utiliser un seul outil pour effectuer une recherche dans les deux types de données archivées. Pour plus d’informations, reportez-vous [à configurer Skype entreprise Server pour l’utilisation de l’archivage Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologies et composants

Les seuls composants requis pour la messagerie instantanée et la présence sont :
  
- Les serveurs front-end de votre organisation (appelés pool) ou un serveur Standard Edition Server. Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs. Pour plus d’informations sur les topologies de pool frontal et la gestion, voir la [disponibilité et la gestion du pool frontal](high-availability-and-disaster-recovery/high-availability.md).
    
- Un programme d’équilibrage de la charge, si vous avez un pool frontal Enterprise Edition.
    
### <a name="supported-collocation"></a>Colocalisation prise en charge

La colocalisation est définie comme étant un serveur unique ou un groupe de serveurs avec plusieurs rôles installés. Pour plus d’informations sur la colocalisation, voir [notions de base de la topologie pour Skype entreprise Server](topology-basics/topology-basics.md). 
  


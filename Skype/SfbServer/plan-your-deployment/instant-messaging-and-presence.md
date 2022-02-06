---
title: Planifier la messagerie instantanée et la présence dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Résumé : Découvrez comment planifier la messagerie instantanée et la présence dans Skype Entreprise Server.'
---

# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planifier la messagerie instantanée et la présence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment planifier la messagerie instantanée et la présence dans Skype Entreprise Server.
  
Planifiez la messagerie instantanée et la présence dans Skype Entreprise Server. Pour en savoir plus sur les options de déploiement spécifiques, telles que l’activation ou la désactivation de la messagerie instantanée hors connexion, voir Déployer la messagerie instantanée et la présence [dans Skype Entreprise Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planifier la messagerie instantanée et la présence dans Skype Entreprise Server

Les serveurs frontux fournissent des fonctionnalités de Skype Entreprise Server essentielles telles que la messagerie instantanée et la présence, et sont inclus dans chaque déploiement Skype Entreprise Server de messagerie instantanée. Deux éditions sont disponibles : Skype Entreprise Server Êdition Entreprise, qui est principalement conçu pour les grandes organisations, et Skype Entreprise Server Édition Standard , qui est conçu principalement pour les petites organisations qui souhaitent un plus petit investissement matériel et ne nécessitent pas d’options de haute disponibilité complètes. Les deux éditions sont Skype Entreprise Server charges de travail de messagerie instantanée, de présence, de conférence et de Voix Entreprise.
  
La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels.. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. Un participant à une conversation de messagerie instantanée peut ajouter un troisième participant à la conversation à tout moment. Lorsque cela arrive, la fenêtre Conversation change pour prendre en charge des fonctionnalités de conférence.
  
La présence fournit des informations aux utilisateurs sur l’état d’autres personnes sur le réseau. L’état de présence d’un utilisateur fournit des informations pour aider les autres utilisateurs à décider s’ils doivent essayer de contacter l’utilisateur et s’ils doivent utiliser la messagerie instantanée, le téléphone ou le courrier électronique. La présence permet une communication instantanée lorsque cela est possible, mais fournit aussi des informations indiquant si un utilisateur est en réunion ou hors du bureau, indiquant que la communication instantanée n’est pas possible. Cet état de présence s’affiche sous la forme d’une icône de présence dans Skype Entreprise et d’autres applications sensibles à la présence, notamment le client de messagerie et de collaboration Microsoft Outlook, les technologies Microsoft SharePoint et les Microsoft Office. L’icône de présence représente la disponibilité actuelle de l’utilisateur et sa volonté de communiquer. 
  
### <a name="technical-requirements"></a>Exigences techniques

La messagerie instantanée et la présence s’exécutent toujours sur Êdition Entreprise pools frontux et Édition Standard serveurs. Pour plus d’informations sur le matériel, les systèmes d’exploitation et les logiciels de base de données pris en charge, voir [Passerelles certifiées](../../SfbPartnerCertification/certification/infra-gateways.md), Configuration requise pour votre environnement [Skype Entreprise 2015](requirements-for-your-environment/requirements-for-your-environment.md) et Configuration requise pour l’infrastructure [pour Skype Entreprise Server 2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Activation de la communication avec des utilisateurs externes

Vous pouvez clairement accroître les avantages de votre investissement dans Skype Entreprise Server en permettant à vos utilisateurs de communiquer avec des utilisateurs externes. Les utilisateurs externes peuvent inclure les catégories suivantes :
  
- Utilisateurs distants : les utilisateurs de votre organisation, lorsqu’ils travaillent en dehors de vos pare-feu et utilisent leurs ordinateurs portables ou d’autres Skype Entreprise Server réseau.
    
- Utilisateurs fédérés : utilisateurs des entreprises avec qui vous travaillez et qui exécutent également Skype Entreprise Server. Pour autoriser vos utilisateurs à contacter facilement ces utilisateurs, créez des relations fédérées avec ces entreprises. 
    
- Skype utilisateurs : Skype Entreprise utilisateurs peuvent atteindre les centaines de millions d’utilisateurs sur Skype messagerie instantanée, vocale et vidéo.
    
> [!NOTE]
> AOL, Yahoo et Google Talk ne sont plus pris en charge. 
  
> [!NOTE]
> Pour activer l’un ou l’ensemble de ces scénarios, vous devez déployer un serveur Edge pour permettre la sécurisation des communications entre votre déploiement Skype Entreprise Server et les utilisateurs externes. Les utilisateurs distants et les utilisateurs d’organisations fédérées de votre organisation pourront voir la présence des autres utilisateurs et communiquer à l’aide de la messagerie instantanée. 
  
> [!NOTE]
> Le protocole XMPP (Extensible Messaging and Presence Protocol) est uniquement pris en charge pour les scénarios de certification JITC (Joint Interoperability Test Command) de la plateforme de collaboration de fonctionnalités unifiées (UCCP). 
  
### <a name="archiving-im-content"></a>Archivage du contenu de messagerie instantanée

Skype Entreprise Server fournit des fonctionnalités que vous pouvez utiliser si votre organisation doit respecter les réglementations de conformité. Vous pouvez utiliser l’archivage pour archiver le contenu des messages instantanés pour tous les utilisateurs de votre organisation ou uniquement pour certains utilisateurs que vous spécifiez. Pour plus d’informations, [voir Plan for archiving in Skype Entreprise Server](archiving/archiving.md). 
  
Si vous avez également déployé Microsoft Exchange Server 2013, vous pouvez intégrer l’archivage des données Exchange à l’archivage des données Skype Entreprise Server et utiliser un seul outil pour rechercher les deux types de données archivées. Pour plus d’informations, [voir Configure Skype Entreprise Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologies et composants

Les seuls composants requis pour la messagerie instantanée et la présence sont :
  
- Serveurs frontux de votre organisation (appelés pool) ou serveur Édition Standard serveur. Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs. Pour plus d’informations sur les topologies et la gestion des pool frontaux, voir la haute disponibilité et [la gestion du pool frontal](high-availability-and-disaster-recovery/high-availability.md).
    
- Un équilibreur de charge, si vous avez un pool Êdition Entreprise frontal.
    
### <a name="supported-collocation"></a>C cocation prise en charge

La cocation est définie comme ayant un serveur unique, ou un groupe de serveurs, avec plusieurs rôles installés. Pour plus d’informations sur la cocation, voir [Topology Basics for Skype Entreprise Server](topology-basics/topology-basics.md). 
  


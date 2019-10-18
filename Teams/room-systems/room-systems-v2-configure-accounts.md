---
title: Configurer des comptes pour les salles de Microsoft teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Consultez cette rubrique pour en savoir plus sur la configuration des comptes pour les salles Microsoft teams dans Exchange et Skype entreprise.
ms.openlocfilehash: 287ebcd421a41f088774920a2ec655ac7c562038
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573615"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurer des comptes pour les salles de Microsoft teams
 
Consultez cette rubrique pour en savoir plus sur les salles de Microsoft teams et son intégration à Exchange et Skype entreprise.
  
Cette rubrique présente la création de comptes utilisés par des salles Microsoft teams dans Microsoft Exchange et Skype entreprise. Pour obtenir des instructions sur le déploiement des appareils de Microsoft Teams, reportez-vous à [la configuration d’une console Microsoft teams](console.md). Votre infrastructure peut correspondre à l’une des configurations suivantes :
  
- Déploiement en ligne : l’environnement de votre organisation est déployé entièrement sur Office 365. Pour plus d’informations, reportez-vous à la rubrique [déploiement de salles Microsoft teams avec Office 365](with-office-365.md).
    
- Déploiement local : votre organisation dispose de serveurs qui contrôlent la façon dont Active Directory, Exchange et Skype entreprise Server sont hébergés. Pour plus d’informations, reportez-vous à la rubrique [déploiement de salles de Microsoft teams avec Skype entreprise Server](with-skype-for-business-server-2015.md)
    
- Déploiements hybrides : votre organisation a une combinaison de services, avec une partie hébergée en local et une partie hébergée en ligne via Office 365. Grâce aux salles de Microsoft Teams, les scénarios hybrides suivants sont pris en charge : 
    
  - Exchange Online avec Skype entreprise Server en local. Pour plus d’informations, reportez-vous à la rubrique [déploiement de salles Microsoft teams avec Exchange Online (hybride)](with-exchange-online.md).
    
  - Échangez en local avec Microsoft teams ou Skype entreprise online. Pour plus d’informations, reportez-vous à la rubrique [déploiement de salles de Microsoft teams avec Exchange en local (hybride)](with-exchange-on-premises.md).
    
La procédure de préparation de l’installation de l’appareil dépend de votre type de configuration.
  
Les salles de Microsoft teams doivent disposer d’un « compte d’appareil » dans Active Directory, d’Exchange et de Skype entreprise. Le compte est utilisé pour accéder à son calendrier de réunion et établir une connectivité Microsoft teams ou Skype entreprise. Les utilisateurs peuvent réserver ce compte en planifiant une réunion à l’aide de celui-ci. Les salles de Microsoft teams seront en mesure de rejoindre cette réunion et de proposer diverses fonctionnalités aux participants de la réunion.
  
> [!IMPORTANT]
> Sans compte d’appareil, aucune de ces fonctionnalités ne fonctionne. 
  
Chaque compte d’appareil est unique pour une seule salle Microsoft teams et nécessite une configuration :
  
- Le compte de l’appareil doit être correctement configuré.
    
- Votre infrastructure doit être configurée pour permettre aux salles de Microsoft teams de valider le compte de l’appareil et d’accéder aux services Microsoft appropriés.
    
> [!IMPORTANT]
> Il est vivement recommandé de créer ce compte bien avant l’installation effective du matériel. Si possible, la préparation du compte devrait commencer 2 à 3 semaines avant l’installation. Dans les environnements hybrides, le compte utilisé pour les salles de Microsoft teams doit disposer de la synchronisation de mot de passe activée dans la synchronisation AAD, car l’authentification Microsoft teams pièces nécessite l’authentification Office 365.
  
Vous pouvez considérer un compte d’appareil comme le compte de ressources reconnu par les utilisateurs comme une salle de conférence ou un compte d’espace de réunion. Lorsque vous souhaitez planifier une réunion qui se déroulera dans cette salle de réunion, vous invitez le compte à cette réunion. Pour utiliser la plupart des salles de Microsoft Teams, vous devez procéder de la même façon avec le compte d’appareil qui est attribué à chacun d’eux.
  
Si vous disposez déjà d’un compte de boîte aux lettres de ressources configuré pour l’espace de réunion dans lequel vous installez les salles de Microsoft Teams, vous pouvez changer ce compte en compte d’appareil. Une fois cette opération terminée, il vous suffit d’ajouter le compte de l’appareil à un appareil Microsoft Teams. Voir exemples de configuration de compte d’appareil fourni ci-dessous.
  
Dans le cadre de la configuration supplémentaire, la gestion à distance est possible à l’aide de l’outil Moniteur Microsoft Azure, comme décrit dans la rubrique planification de la [gestion des salles de Microsoft teams avec Azure Monitor](azure-monitor-plan.md), déploiement de la [gestion de](azure-monitor-deploy.md) [Microsoft teams Gestion des appareils Microsoft teams](azure-monitor-manage.md) 
  
## <a name="basic-configuration"></a>Configuration de base

Ces propriétés représentent la configuration minimale d’un compte d’appareil pour fonctionner avec les salles de Microsoft Teams. Votre compte d’appareil doit nécessiter une configuration supplémentaire.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Boîte aux lettres Exchange (Exchange 2013 SP1 ou version ultérieure, ou Exchange Online)  <br/> |Le fait d’activer le compte auprès d’une boîte aux lettres Exchange donne au compte de l’appareil la possibilité de recevoir et d’envoyer des demandes de messages et de réunion, et d’afficher un calendrier de réunions sur l’appareil Microsoft Teams. La boîte aux lettres de Microsoft teams doit être une boîte aux lettres de salle.  <br/> |
|Skype entreprise est activé  <br/> |Skype entreprise doit être activé pour pouvoir utiliser différentes fonctions de conférence, comme les appels vidéo, la messagerie instantanée et le partage d’écran. La prise en charge de Skype entreprise Online et de Skype entreprise Server est prise en charge.  <br/> |
|Activation par mot de passe  <br/> |Le compte de l’appareil doit être activé avec un mot de passe, ou il ne peut pas s’authentifier auprès d’Exchange ou de Skype entreprise Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuration avancée

Si les propriétés de la configuration de base permettent de configurer le compte de l’appareil dans un environnement simple, il est possible que votre environnement dispose d’autres restrictions sur les comptes d’annuaire qui doivent être remplies pour que Microsoft teams utilise correctement le compte d’appareil.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Authentification basée sur un certificat  <br/> |Des certificats sont requis pour Exchange et Skype entreprise Server. Pour déployer les certificats, vous devez les charger lorsque vous vous connectez en tant qu’administrateur.  <br/> |
   
Le moyen le plus simple de configurer des comptes de périphériques consiste à les configurer à l’aide de Windows PowerShell distant. Microsoft fournit [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script permettant de créer de nouveaux comptes d’appareils, ou de valider des comptes de ressources existants dont vous avez besoin pour vous aider à les convertir en comptes d’appareils Microsoft teams compatibles.
  
Si vous préférez utiliser l’interface utilisateur d’Office 365 sur des cmdlets Windows PowerShell, certaines étapes peuvent être effectuées manuellement. Voir [création d’un compte d’appareil à l’aide d’Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Voir aussi

[Plan pour les salles de Microsoft teams](skype-room-systems-v2-0.md)
  
[Configurer une console de salle Microsoft teams](console.md)
  
[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)


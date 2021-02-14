---
title: Configurer des comptes pour des salles Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Lisez cette rubrique pour en savoir plus sur la configuration des comptes pour les salles Microsoft Teams dans Exchange et Skype Entreprise.
ms.openlocfilehash: e171ef22dd1733c06b03a4a9483f591d73d70cb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662519"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurer des comptes pour des salles Microsoft Teams
 
Lisez cette rubrique pour en savoir plus sur les salles Microsoft Teams et la manière dont elles sont intégrées à Exchange et Skype Entreprise.
  
Cette rubrique présente la création de comptes utilisés par les salles Microsoft Teams dans Microsoft Exchange et Skype Entreprise. Les instructions de déploiement pour les appareils Salles Microsoft Teams sont couvertes [dans La configuration d’une console salles Microsoft Teams.](console.md) Votre infrastructure peut correspondre à l’une des configurations suivantes :
  
- Déploiement en ligne : l’environnement de votre organisation est entièrement déployé sur Microsoft 365 ou Office 365. Pour plus d’informations, voir Déployer des salles Microsoft Teams avec [Microsoft 365 ou Office 365.](with-office-365.md)
    
- Déploiement local : votre organisation possède des serveurs qu’elle contrôle, où Active Directory, Exchange et Skype Entreprise Server sont hébergés. Pour plus d’informations, [voir Déployer des salles Microsoft Teams avec Skype Entreprise Server](with-skype-for-business-server-2015.md)
    
- Déploiements hybrides : votre organisation possède un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne via Microsoft 365 ou Office 365. Avec Salles Microsoft Teams, les scénarios hybrides suivants sont pris en charge :
    
  - Exchange Online avec Skype Entreprise Server en local. Pour plus d’informations, voir [Déployer des salles Microsoft Teams avec Exchange Online (hybride).](with-exchange-online.md)
    
  - Exchange en local avec Microsoft Teams ou Skype Entreprise Online. Pour plus d’informations, voir Déployer des salles Microsoft Teams avec [Exchange en local (hybride).](with-exchange-on-premises.md)
    
La procédure de préparation de l’installation de l’appareil dépend de votre type de configuration.
  
Les salles Microsoft Teams doivent être affectées à un « compte d’appareil » dans Active Directory, Exchange et Skype Entreprise. Le compte est utilisé pour accéder à son calendrier de réunions et établir une connectivité Microsoft Teams ou Skype Entreprise. Les utilisateurs peuvent réserver ce compte en planifiant une réunion à l’aide de celui-ci. Les salles Microsoft Teams pourront rejoindre cette réunion et offrir différentes fonctionnalités aux participants à la réunion.
  
> [!IMPORTANT]
> Sans compte d’appareil, aucune de ces fonctionnalités ne fonctionne. 
  
Chaque compte d’appareil est unique sur un seul appareil Salles Microsoft Teams et nécessite une configuration :
  
- Le compte de l’appareil doit être configuré correctement.
    
- Votre infrastructure doit être configurée pour permettre aux salles Microsoft Teams de valider le compte de l’appareil et d’accéder aux services Microsoft appropriés.
    
> [!IMPORTANT]
> Il est vivement recommandé de créer ce compte bien avant l’installation effective du matériel. Si possible, la préparation du compte devrait commencer 2 à 3 semaines avant l’installation. 

Dans les environnements hybrides, le compte utilisé pour les salles Microsoft Teams doit avoir la synchronisation des mots de passe activée dans la synchronisation Azure Active Directory (AAD), car l’authentification salles Microsoft Teams nécessite l’authentification Microsoft 365 ou Office 365. Lors de la configuration du compte, assurez-vous que l’adresse SIP du compte correspond à son nom d’utilisateur principal (UPN) dans AAD. 
  
Vous pouvez voir un compte d’appareil comme un compte de ressource que les utilisateurs reconnaissent comme étant un compte de salle de conférence ou d’espace de réunion. Lorsque vous souhaitez planifier une réunion qui se déroulera dans cette salle de réunion, vous invitez le compte à cette réunion. Pour utiliser les salles Microsoft Teams de façon efficace, vous devez faire de même avec le compte d’appareil affecté à chacune d’elles.
  
Si vous avez déjà un compte de boîte aux lettres de ressources installé pour l’espace de réunion où vous installez les salles Microsoft Teams, vous pouvez changer ce compte de ressource en compte d’appareil. Une fois cette opération effectuée, il vous suffit d’ajouter le compte de l’appareil sur un appareil Microsoft Teams Rooms. Consultez les exemples de configuration de compte d’appareil fournis ci-dessous.
  
Avec une configuration supplémentaire, la gestion à distance est possible à l’aide de Microsoft Azure Monitor comme décrit dans la gestion de salles Microsoft Teams avec [Azure Monitor,](azure-monitor-plan.md)déployer la gestion des salles Microsoft Teams avec [Azure Monitor](azure-monitor-deploy.md)et gérer les appareils [Salles Microsoft Teams](azure-monitor-manage.md)avec Azure Monitor. 
  
## <a name="basic-configuration"></a>Configuration de base

Ces propriétés représentent la configuration minimale pour qu’un compte d’appareil fonctionne avec les salles Microsoft Teams. Votre compte d’appareil peut nécessiter une configuration plus complexe.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Boîte aux lettres Exchange (Exchange 2013 SP1 ou version ultérieure, ou Exchange Online)  <br/> |L’activation du compte avec une boîte aux lettres Exchange permet au compte d’appareil de recevoir et d’envoyer des messages électroniques et des demandes de réunion, et d’afficher un calendrier de réunions sur l’appareil Salles Microsoft Teams. La boîte aux lettres Salles Microsoft Teams doit être une boîte aux lettres de salle.  <br/> |
|Skype Entreprise est activé  <br/> |Skype Entreprise doit être activé pour pouvoir utiliser différentes fonctionnalités de conférence, telles que les appels vidéo, la messagerie instantanée et le partage d’écran. Skype Entreprise Online et Skype Entreprise Server sont pris en charge.  <br/> |
|Activation par mot de passe  <br/> |Le compte de l’appareil doit être activé avec un mot de passe ou ne peut pas s’authentifier auprès d’Exchange ou de Skype Entreprise Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuration avancée

Bien que les propriétés de la configuration de base autorisent la configuration du compte de l’appareil dans un environnement simple, il est possible que votre environnement ait d’autres restrictions sur les comptes d’annuaire qui doivent être respectées pour que les salles Microsoft Teams utilisent correctement le compte d’appareil.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Authentification basée sur un certificat  <br/> |Des certificats peuvent être requis pour Exchange et Skype Entreprise Server. Pour déployer les certificats, vous devez les charger lorsque vous vous connectez en tant qu’administrateur.  <br/> |
   
La manière la plus simple de configurer des comptes d’appareil consiste à les configurer à l’aide de la Windows PowerShell. Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer de nouveaux comptes d’appareils, ou à valider les comptes de ressources existants que vous avez afin de vous aider à les transformer en comptes d’appareils Microsoft Teams rooms compatibles.
  
Si vous préférez utiliser l’interface utilisateur de Microsoft 365 ou d’Office 365 par rapport à Windows PowerShell cmdlets, certaines étapes peuvent être effectuées manuellement. Voir [Créer un compte d’appareil à l’aide de Microsoft 365 ou Office 365.](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>Voir aussi

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)


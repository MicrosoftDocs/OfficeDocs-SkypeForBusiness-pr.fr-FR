---
title: Configurer des comptes pour Salles Microsoft Teams
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
description: Lisez cette rubrique pour en savoir plus sur la configuration de comptes pour Salles Microsoft Teams dans Exchange et Skype Entreprise.
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117472"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurer des comptes pour Salles Microsoft Teams
 
Lisez cette rubrique pour en savoir Salles Microsoft Teams et comment elle s’intègre à Exchange et Skype Entreprise.
  
Cette rubrique présente comment créer des comptes utilisés par Salles Microsoft Teams dans Microsoft Exchange et Skype Entreprise. Les instructions de déploiement Salles Microsoft Teams appareils mobiles sont couvertes [dans Configurer une console Salles Microsoft Teams données.](console.md) Votre infrastructure peut correspondre à l’une des configurations suivantes :
  
- Déploiement en ligne : l’environnement de votre organisation est entièrement déployé sur Microsoft 365 ou Office 365. Pour plus d’informations, [voir Déployer Salles Microsoft Teams avec Microsoft 365 ou Office 365.](with-office-365.md)
    
- Déploiement local : votre organisation possède des serveurs qu’elle contrôle, où Active Directory, Exchange et Skype Entreprise Server sont hébergés. Pour plus d’informations, voir [Déployer Salles Microsoft Teams avec Skype Entreprise Server](with-skype-for-business-server-2015.md)
    
- Déploiements hybrides : votre organisation possède un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne via Microsoft 365 ou Office 365. Avec Salles Microsoft Teams, les scénarios hybrides suivants sont pris en charge :
    
  - Exchange Online avec Skype Entreprise Server local. Pour plus d’informations, [voir Déployer Salles Microsoft Teams avec Exchange Online (hybride).](with-exchange-online.md)
    
  - Exchange local avec Microsoft Teams ou Skype Entreprise Online. Pour plus d’informations, [voir Déployer Salles Microsoft Teams avec Exchange local (hybride).](with-exchange-on-premises.md)
    
La procédure de préparation de l’installation de l’appareil dépend de votre type de configuration.
  
Salles Microsoft Teams doit être affecté à un « compte d’appareil » dans Active Directory, Exchange et Skype Entreprise. Le compte est utilisé pour accéder à son calendrier de réunion et établir Microsoft Teams ou Skype Entreprise connexion. Les utilisateurs peuvent réserver ce compte en planifiant une réunion à l’aide de celui-ci. Salles Microsoft Teams pourront participer à cette réunion et proposer différentes fonctionnalités aux participants à la réunion.
  
> [!IMPORTANT]
> Sans compte d’appareil, aucune de ces fonctionnalités ne fonctionne. 
  
Chaque compte d’appareil est propre à un seul Salles Microsoft Teams et nécessite une configuration :
  
- Le compte de l’appareil doit être configuré correctement.
    
- Votre infrastructure doit être configurée pour permettre aux utilisateurs Salles Microsoft Teams valider le compte de l’appareil et d’atteindre les utilisateurs services Microsoft.
    
> [!IMPORTANT]
> Il est vivement recommandé de créer ce compte bien avant l’installation effective du matériel. Si possible, la préparation du compte devrait commencer 2 à 3 semaines avant l’installation. 

Dans les environnements hybrides, le compte utilisé pour Salles Microsoft Teams doit activer la synchronisation des mots de passe dans la synchronisation Azure Active Directory (AAD), car l’authentification Salles Microsoft Teams nécessite une authentification Microsoft 365 Office 365 utilisateur. Lors de la configuration du compte, assurez-vous que l’adresse SIP du compte correspond à son nom d’utilisateur principal (UPN) dans AAD. 
  
Vous pouvez voir un compte d’appareil comme le compte de ressource que les utilisateurs reconnaissent comme étant un compte de salle de conférence ou d’espace de réunion. Lorsque vous souhaitez planifier une réunion qui se déroulera dans cette salle de réunion, vous invitez le compte à cette réunion. Pour utiliser les Salles Microsoft Teams de façon efficace, vous faites de même avec le compte d’appareil qui est affecté à chacun d’eux.
  
Si vous avez déjà un compte de boîte aux lettres de ressources créé pour l’espace de réunion dans lequel vous installez Salles Microsoft Teams, vous pouvez changer ce compte de ressource en compte d’appareil. Une fois que c’est fait, il vous suffit d’ajouter le compte de l’appareil à un Salles Microsoft Teams appareil. Consultez les exemples de configuration de compte d’appareil fournis ci-dessous.
  
Avec une configuration supplémentaire, la gestion à distance est possible à l’aide de Microsoft Azure Monitor, comme décrit dans la gestion de plan Salles Microsoft Teams avec Azure Monitor, Déployer la gestion [de l’Salles Microsoft Teams](azure-monitor-deploy.md)avec Azure Monitor et Gérer les appareils Salles Microsoft Teams avec [Azure](azure-monitor-manage.md) [Monitor.](azure-monitor-plan.md) 
  
## <a name="basic-configuration"></a>Configuration de base

Ces propriétés représentent la configuration minimale pour un compte d’appareil à Salles Microsoft Teams. Votre compte d’appareil peut nécessiter une configuration plus complexe.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Exchange boîte aux lettres (Exchange 2013 SP1 ou ultérieure, ou Exchange Online)  <br/> |L’activation du compte avec une boîte aux lettres Exchange permet au compte d’appareil de recevoir et d’envoyer des messages électroniques et des demandes de réunion, et d’afficher un calendrier de réunions sur l Salles Microsoft Teams appareil. La Salles Microsoft Teams doit être une boîte aux lettres de salle.  <br/> |
|Skype Entreprise est activé  <br/> |Skype Entreprise d’écran doivent être activés pour pouvoir utiliser différentes fonctionnalités de conférence, telles que les appels vidéo, la messagerie instantanée et le partage d’écran. Les Skype Entreprise Online et Skype Entreprise Server sont pris en charge.  <br/> |
|Activation par mot de passe  <br/> |Le compte de l’appareil doit être activé avec un mot de passe ou ne peut pas s’authentifier auprès Exchange ou Skype Entreprise Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuration avancée

Bien que les propriétés de la configuration de base autorisent la configuration du compte d’appareil dans un environnement simple, il est possible que votre environnement ait d’autres restrictions sur les comptes d’annuaire qui doivent être respectées pour que Salles Microsoft Teams utilise correctement le compte d’appareil.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Authentification basée sur un certificat  <br/> |Des certificats peuvent être requis pour les certificats Exchange et Skype Entreprise Server. Pour déployer les certificats, vous devez les charger lorsque vous vous connectez en tant qu’administrateur.  <br/> |
   
La manière la plus simple de configurer des comptes d’appareil consiste à les configurer à l’aide de la Windows PowerShell. Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer de nouveaux comptes d’appareils, ou à valider les comptes de ressources existants que vous avez pour vous aider à les transformer en comptes d’appareils Salles Microsoft Teams compatibles.
  
Si vous préférez utiliser l’interface utilisateur Microsoft 365 ou Office 365'Windows PowerShell, vous pouvez effectuer certaines étapes manuellement. Voir [Créer un compte d’appareil à](/surface-hub/create-a-device-account-using-office-365)Microsoft 365 ou Office 365.
  
## <a name="see-also"></a>Voir aussi

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)
---
title: Configurer des comptes pour Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Lisez cette rubrique pour en savoir plus sur la configuration de comptes Salles Microsoft Teams dans Exchange et Skype Entreprise.
ms.openlocfilehash: 9c898d63291d6b2d4a8d2557f2e307156b3487b4
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503491"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurer des comptes pour Salles Microsoft Teams
 
Lisez cette rubrique pour en savoir Salles Microsoft Teams et comment elle s’intègre à Exchange et Skype Entreprise.
  
Cette rubrique présente la création de comptes utilisés par les utilisateurs Salles Microsoft Teams Microsoft Exchange et Skype Entreprise. Votre infrastructure peut correspondre à l’une des configurations suivantes :
  
- Déploiement en ligne : l’environnement de votre organisation est entièrement déployé sur Microsoft 365 ou Office 365. Pour plus d’informations, [voir Déployer Salles Microsoft Teams avec Microsoft 365 ou Office 365](with-office-365.md).
    
- Déploiement local : votre organisation possède des serveurs qu’elle contrôle, où Active Directory, Exchange et Skype Entreprise Server sont hébergés. Pour plus d’informations, voir [Déployer Salles Microsoft Teams avec Skype Entreprise Server](with-skype-for-business-server-2015.md)
    
- Déploiements hybrides : votre organisation possède un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne via Microsoft 365 ou Office 365. Avec Salles Microsoft Teams, les scénarios hybrides suivants sont pris en charge :
    
  - Exchange Online avec Skype Entreprise Server local. Pour plus d’informations, [voir Déployer Salles Microsoft Teams déploiement Exchange Online (hybride).](with-exchange-online.md)
    
  - Exchange local avec Microsoft Teams. Pour plus d’informations, [voir Déployer Salles Microsoft Teams avec Exchange local (hybride).](with-exchange-on-premises.md)
    
La procédure de préparation de l’installation de l’appareil dépend de votre type de configuration.
  
Salles Microsoft Teams doit être affecté à un « compte de ressource » dans Active Directory, Exchange et Skype Entreprise. Le compte est utilisé pour accéder à son calendrier de réunion et établir Microsoft Teams ou Skype Entreprise connexion. Les utilisateurs peuvent réserver ce compte en planifiant une réunion à l’aide de celui-ci. Salles Microsoft Teams pourront participer à cette réunion et proposer différentes fonctionnalités aux participants à la réunion.
  
> [!IMPORTANT]
> Sans un compte de ressource, aucune de ces fonctionnalités ne fonctionne. 
  
Chaque compte de ressource est propre à une installation unique Salles Microsoft Teams et nécessite une configuration particulière :
  
- Le compte de ressource doit être configuré correctement.
    
- Votre infrastructure doit être configurée pour permettre aux utilisateurs Salles Microsoft Teams valider le compte de ressource et d’atteindre les ressources services Microsoft.

> [!NOTE] 
> Si vous utilisez Microsoft Teams panneaux, le salles Teams ressource se salles Teams et les panneaux Teams associés.
    
> [!IMPORTANT]
> Il est vivement recommandé de créer ce compte bien avant l’installation effective du matériel. Si possible, la préparation du compte devrait commencer 2 à 3 semaines avant l’installation.
> 

Dans les environnements hybrides, le compte utilisé pour Salles Microsoft Teams doit activer la synchronisation des mots de passe dans la synchronisation Azure Active Directory (AAD), car l’authentification Salles Microsoft Teams nécessite Microsoft 365 ou Office 365'authentification. Lors de la configuration du compte, assurez-vous que l’adresse SIP du compte correspond à son nom d’utilisateur principal (UPN) dans AAD. 
  
Vous pouvez voir un compte de ressource comme le compte de ressource que les utilisateurs reconnaissent comme étant un compte de salle de conférence ou d’espace partagé. Lorsque vous souhaitez planifier une réunion à l’aide de cet espace, vous invitez le compte à cette réunion.
  
Si vous avez déjà un compte de boîte aux lettres de ressources créé pour l’espace sur lequel vous installez Salles Microsoft Teams, vous pouvez changer ce compte en un salles Teams ressource. Une fois que c’est fait, il vous suffit de vous Salles Microsoft Teams à ce compte.
  
## <a name="basic-configuration"></a>Configuration de base

Ces propriétés représentent la configuration minimale pour qu’un compte de ressource Salles Microsoft Teams. Votre compte de ressource peut nécessiter une configuration plus grande.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Exchange boîte aux lettres (Exchange 2013 SP1 ou ultérieure, ou Exchange Online)  <br/> |L’activation du compte avec une boîte aux lettres Exchange permet au compte de ressource de recevoir et d’envoyer des messages électroniques et des demandes de réunion, et d’afficher un calendrier de réunions sur l Salles Microsoft Teams appareil. La Salles Microsoft Teams doit être une boîte aux lettres de salle.  <br/> |
|Skype Entreprise est activé  <br/> |Skype Entreprise peut être activé afin d’utiliser différentes fonctionnalités de Skype Entreprise conférence, telles que les appels vidéo, la messagerie instantanée et le partage d’écran.  <br/> |
|Activation par mot de passe  <br/> |Le compte de ressource doit être activé avec un mot de passe ou ne peut pas s’authentifier avec des Microsoft Teams, des Exchange ou des Skype Entreprise Server. L’expiration du mot de passe doit être désactivée sur tous salles Teams de ressources.   <br/> |
   
## <a name="advanced-configuration"></a>Configuration avancée

Bien que les propriétés de la configuration de base autorisent la configuration du compte de ressource dans un environnement simple, il est possible que votre environnement ait d’autres restrictions sur les comptes d’annuaire qui doivent être respectées pour que Salles Microsoft Teams utilise correctement le compte de ressource.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Authentification basée sur un certificat  <br/> |Des certificats peuvent être requis pour les certificats Exchange et Skype Entreprise Server. Pour déployer les certificats, vous devez les charger lorsque vous vous connectez en tant qu’administrateur.  <br/> |
  
## <a name="see-also"></a>Voir aussi

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

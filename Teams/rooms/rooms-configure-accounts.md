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
description: Lisez cette rubrique pour en savoir plus sur la configuration des comptes pour Salles Microsoft Teams (y Surface Hub) et les téléphones en zone commune.
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514729"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurer des comptes pour Salles Microsoft Teams
 
Cette rubrique explique comment créer des comptes utilisés par Salles Microsoft Teams. Votre infrastructure peut correspondre à l’une des configurations suivantes :
  
- Déploiement en ligne : l’environnement de votre organisation est entièrement déployé sur Microsoft 365 ou Office 365.
    
- Déploiement local : votre organisation possède des serveurs qu’elle contrôle, où Active Directory, Exchange et Skype Entreprise Server sont hébergés. Pour plus d’informations, voir [Déployer Salles Microsoft Teams avec Skype Entreprise Server](with-skype-for-business-server-2015.md)
    
- Déploiements hybrides : votre organisation possède un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne via Microsoft 365 ou Office 365. Avec Salles Microsoft Teams, les scénarios hybrides suivants sont pris en charge :
    
  - Exchange Online avec Skype Entreprise Server local.
    
  - Exchange local avec Microsoft Teams.
    
La procédure de préparation de l’installation de l’appareil dépend de votre type de configuration.
  
Salles Microsoft Teams avoir un « compte de ressource » dans Active Directory, un compte de Exchange et (le cas échéant) une Skype Entreprise. Le compte est utilisé pour accéder au calendrier de la réunion et établir Microsoft Teams et/ou Skype Entreprise connexion. Les utilisateurs peuvent réserver ce compte en planifiant une réunion à l’aide de celui-ci. Salles Microsoft Teams pourront participer à cette réunion et proposer différentes fonctionnalités aux participants à la réunion.
  
> [!IMPORTANT]
> Sans un compte de ressource, aucune de ces fonctionnalités ne fonctionne.
  
Chaque compte de ressource est propre à Salles Microsoft Teams installation.
  
- Le compte de ressource doit être configuré correctement.
    
- Votre infrastructure doit être configurée pour permettre aux utilisateurs Salles Microsoft Teams valider le compte de ressource et d’atteindre les ressources services Microsoft.

> [!NOTE] 
> Si vous utilisez Microsoft Teams panneaux, le salles Teams ressource se salles Teams et les panneaux Teams associés.
    
> [!IMPORTANT]
> Il est vivement recommandé de créer ce compte bien avant l’installation effective du matériel. Si possible, la préparation du compte devrait commencer 2 à 3 semaines avant l’installation.
> 
Dans les environnements hybrides qui n’utilisent pas Skype Entreprise, il est fortement recommandé de créer le compte en mode natif dans Azure Active Directory. Si le compte doit être créé à l’aide d’Active Directory local, la synchronisation des mots de passe doit être activée dans la synchronisation Azure Active Directory (AAD Connecter), car l’authentification Salles Microsoft Teams nécessite Microsoft 365 ou Office 365'authentification. Lors de la configuration du compte, assurez-vous que l’adresse de messagerie du compte correspond à son nom d’utilisateur principal (UPN) dans AAD. 
  
Vous pouvez voir un compte de ressource comme le compte que les utilisateurs reconnaissent comme étant le nom d’une salle de conférence ou d’un espace partagé. Lorsque vous souhaitez planifier une réunion à l’aide de cet espace, vous invitez le compte de ressource à cette réunion.
  
Si vous avez déjà un compte de boîte aux lettres de ressources Exchange déjà créé pour l’espace sur lequel vous installez Salles Microsoft Teams, vous pouvez changer ce compte en un compte de ressource salles Teams personnel. Une fois que c’est fait, il vous suffit de vous Salles Microsoft Teams à ce compte.
  
## <a name="basic-configuration"></a>Configuration de base

Ces propriétés représentent la configuration minimale pour qu’un compte de ressource Salles Microsoft Teams. Votre compte de ressource peut nécessiter une configuration plus grande.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Exchange boîte aux lettres (Exchange 2013 SP1 ou ultérieure, ou Exchange Online)  <br/> |La boîte Exchange permet au compte de ressource de recevoir et d’envoyer des messages et des demandes de réunion, et d’afficher un calendrier de réunions sur Salles Microsoft Teams. La Salles Microsoft Teams doit être une boîte aux lettres de ressource de type « salle ».  <br/> |
|Skype Entreprise est activé  <br/> |Skype Entreprise peut être activé afin d’utiliser différentes fonctionnalités de Skype Entreprise conférence, telles que les appels vidéo, la messagerie instantanée et le partage d’écran.  <br/> |
|Activation par mot de passe  <br/> |Le compte de ressource doit être activé avec un mot de passe ou ne peut pas s’authentifier avec des Microsoft Teams, des Exchange ou des Skype Entreprise Server. L’expiration du mot de passe doit être désactivée sur tous salles Teams de ressources.   <br/> |
   
## <a name="advanced-configuration"></a>Configuration avancée

Bien que les propriétés de la configuration de base autorisent la configuration du compte de ressource dans un environnement simple, il est possible que votre environnement ait d’autres restrictions sur les comptes qui doivent être respectées pour que Salles Microsoft Teams utilise correctement le compte de ressource.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Authentification basée sur un certificat  <br/> |Des certificats peuvent être requis pour les certificats Exchange et Skype Entreprise Server. Pour déployer les certificats, vous devez les charger lorsque vous vous connectez en tant qu’administrateur.  <br/> |

## <a name="see-also"></a>Voir aussi

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

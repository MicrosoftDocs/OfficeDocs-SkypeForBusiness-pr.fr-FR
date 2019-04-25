---
title: Configurer des comptes pour les salles d’équipes Microsoft
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: Lisez cette rubrique pour en savoir plus sur la configuration de comptes pour les salles d’équipes Microsoft dans Exchange et Skype pour les entreprises.
ms.openlocfilehash: 7606f31dde96236111b4a44919427245fa32215d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214883"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurer des comptes pour les salles d’équipes Microsoft
 
Lisez cette rubrique pour en savoir plus sur les salles d’équipes Microsoft et comment il s’intègre à Exchange et Skype pour les entreprises.
  
Cette rubrique explique comment créer les comptes utilisés par les salles d’équipes Microsoft dans Microsoft Exchange et Skype pour les entreprises. Instructions de déploiement pour les appareils Microsoft équipes salles est décrite dans [Configure une console Microsoft équipes salles](console.md). Votre infrastructure peut correspondre à l’une des configurations suivantes :
  
- Déploiement en ligne : environnement de votre organisation est déployé entièrement sur Office 365. Pour plus d’informations, voir [Déployer des salles équipes Microsoft avec Office 365](with-office-365.md).
    
- Déploiement sur site : votre organisation dispose de serveurs qu’il contrôle, où sont hébergées Skype pour Business Server, Exchange et Active Directory. Pour plus d’informations, voir [Déployer Microsoft équipes salles avec Skype pour Business Server](with-skype-for-business-server-2015.md)
    
- Déploiements hybrides : votre organisation possède un mélange de services, avec certains hébergés sur site et certaines hébergé en ligne via Office 365. Des espaces d’équipes Microsoft, les scénarios hybrides suivants sont pris en charge : 
    
  - Exchange Online avec Skype pour Business Server localement. Pour plus d’informations, voir [Déployer Microsoft équipes salles avec Exchange Online (hybride)](with-exchange-online.md).
    
  - Exchange sur site avec Skype pour Business en ligne. Pour plus d’informations, voir [Déployer Microsoft équipes salles avec Exchange sur site (hybride)](with-exchange-on-premises.md).
    
La procédure de préparation de l’installation de l’appareil dépend de votre type de configuration.
  
Salles d’équipes Microsoft doit être affecté à un compte « périphériques » dans Active Directory, Exchange et Skype pour les entreprises. Le compte est utilisé pour accéder à son calendrier de la réunion et établir Skype pour Business connectivity. Les utilisateurs peuvent réserver ce compte en planifiant une réunion à l’aide de celui-ci. Salles d’équipes Microsoft sera en mesure de participer à cette réunion et fournir des fonctionnalités différentes aux participants à la réunion.
  
> [!IMPORTANT]
> Sans un compte d’appareil, aucune de ces fonctionnalités fonctionnera. 
  
Chaque compte de l’appareil est unique à un seul périphérique Microsoft équipes salles et configurer :
  
- Le compte de l’appareil doit être configuré correctement.
    
- Votre infrastructure doit être configuré pour autoriser les salles d’équipes Microsoft pour valider le compte de l’appareil et de joindre les services Microsoft appropriés.
    
> [!IMPORTANT]
> Il est vivement recommandé de créer ce compte bien avant l’installation effective du matériel. Si possible, la préparation du compte devrait commencer 2 à 3 semaines avant l’installation. Dans les environnements hybrides, le compte utilisé pour les salles d’équipes Microsoft doit avoir activé dans Sync DAS car l’authentification Microsoft équipes salles requiert une authentification 365 0ffice de synchronisation de mot de passe.
  
Vous pouvez considérer un compte de périphérique en tant que compte la ressource personnes reconnaissent en tant que compte d’une conférence salle de réunion espace ou. Lorsque vous souhaitez planifier une réunion qui se déroulera dans cette salle de réunion, vous invitez le compte à cette réunion. Pour pouvoir utiliser efficacement salles des équipes Microsoft, vous faire de même avec le compte d’appareil qui est affecté à chacune d’elles.
  
Si vous disposez déjà d’un compte de boîte aux lettres de ressources défini pour l’espace de réunion dans lequel vous installez salles des équipes Microsoft, vous pouvez modifier ce compte de ressource à un compte de l’appareil. Une fois cette opération effectuée, il vous souhaitez est ajouter le compte de périphérique pour un périphérique de salles d’équipes Microsoft. Voir exemples de paramètres compte périphérique ci-dessous.
  
Avec une configuration supplémentaire, la gestion à distance est possible à l’aide de Microsoft Azure Monitor comme décrit dans la [gestion de planification Microsoft équipes salles avec Azure moniteur](../../plan-your-deployment/clients-and-devices/azure-monitor.md), la [gestion de déployer Microsoft équipes salles avec Azure moniteur](azure-monitor.md)et [ Gérer les périphériques de salles d’équipes Microsoft Azure moniteur](../../manage/skype-room-systems-v2/azure-monitor.md). 
  
## <a name="basic-configuration"></a>Configuration de base

Ces propriétés représentent la configuration minimale pour un compte de périphérique fonctionner avec Microsoft équipes salles. Votre compte de périphérique peut nécessiter plus poussée du programme d’installation.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Boîte aux lettres Exchange (Exchange 2013 SP1 ou version ultérieure, ou Exchange Online)  <br/> |Activation du compte avec une boîte aux lettres Exchange permet le compte de périphérique pour recevoir et envoyer des messages et demandes de réunion et afficher un calendrier des réunions sur l’appareil de salles d’équipes Microsoft. La boîte aux lettres Microsoft équipes salles doit correspondre à une boîte aux lettres de salle.  <br/> |
|Skype pour les entreprises est activé.  <br/> |Skype pour les entreprises doit être activé pour pouvoir utiliser les diverses fonctionnalités de conférence, comme les appels vidéo, messagerie instantanée et le partage d’écran. Skype pour Business Online et Skype pour Business Server sont prises en charge.  <br/> |
|Activation par mot de passe  <br/> |Le compte de l’appareil doit être activé par un mot de passe, ou il ne peut pas authentifier avec Exchange ou Skype pour Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuration avancée

Pendant les propriétés pour la configuration de base autorisera le compte de l’appareil à être configurée dans un environnement simple, il est possible de votre environnement comporte d’autres restrictions sur les comptes de répertoire qui doivent être remplies pour les salles d’équipes Microsoft utiliser correctement le compte de l’appareil.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Authentification basée sur un certificat  <br/> |Certificats peuvent être requis pour Exchange et Skype pour Business Server. Pour déployer les certificats, vous devez les charger lorsque vous vous connectez en tant qu’administrateur.  <br/> |
   
Pour configurer les comptes de périphérique, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance. Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script permettant de créer des comptes d’appareil ou valider des comptes ressource existante dont vous disposez pour vous aider à les transformer en comptes de périphériques compatibles avec Microsoft équipes salles.
  
Si vous préférez utiliser l’interface utilisateur d’Office 365 sur les applets de commande Windows PowerShell, certaines étapes peuvent être effectuées manuellement. Consultez [Création d’un compte de périphérique à l’aide d’Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Voir aussi

[Planifier des équipes Microsoft salles](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Configurer une console Microsoft équipes salles](console.md)
  
[Gérer Microsoft Teams Rooms](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


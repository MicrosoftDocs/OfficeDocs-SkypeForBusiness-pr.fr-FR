---
title: Configurer des comptes pour les systèmes de salle Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ''
description: Lisez cette rubrique pour en savoir plus sur la configuration des comptes pour les systèmes de salle Skype v2 dans Exchange et Skype pour Business Server 2015.
ms.openlocfilehash: 0514d1b542e8fa53f7210992d5cb219f7e9a7719
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2018
---
# <a name="configure-accounts-for-skype-room-systems-v2"></a>Configurer des comptes pour les systèmes de salle Skype v2
 
Lisez cette rubrique pour en savoir plus sur les systèmes de salle Skype v2 et comment il s’intègre à Exchange et Skype pour Business Server 2015.
  
Cette rubrique explique comment créer les comptes utilisés par les systèmes de salle Skype v2 dans Microsoft Exchange et Skype pour Business Server 2015. Instructions de déploiement pour les appareils v2 Skype salle systèmes est décrite dans [Configure une console v2 de systèmes de salle Skype](console.md). Votre infrastructure peut correspondre à l’une des configurations suivantes :
  
- Déploiement en ligne : environnement de votre organisation est déployé entièrement sur Office 365. Pour plus d’informations, voir [déployer Skype salle systèmes v2 avec Office 365](with-office-365.md).
    
- Déploiement sur site : votre organisation dispose de serveurs qu’il contrôle, où sont hébergées Skype pour Business Server 2015, Exchange et Active Directory. Pour plus d’informations, voir [déployer Skype salle systèmes v2 avec Skype pour Business Server 2015](with-skype-for-business-server-2015.md)
    
- Déploiement hybride : votre organisation possède un mélange de services, avec certains hébergés sur site et certaines hébergé en ligne via Office 365. Avec les systèmes de salle Skype v2, les scénarios hybrides suivants sont pris en charge : 
    
  - Exchange Online avec Skype pour Business Server 2015 localement. Pour plus d’informations, voir [déployer Skype salle systèmes v2 avec Exchange Online (hybride)](with-exchange-online.md).
    
  - Exchange sur site avec Skype pour Business en ligne. Pour plus d’informations, voir [déployer Skype salle systèmes v2 avec Exchange sur site (hybride)](with-exchange-on-premises.md).
    
La procédure de préparation de l’installation de l’appareil dépend de votre type de configuration.
  
Systèmes de salle Skype v2 doit être affectée à un compte d’utilisateur « » dans Active Directory, Exchange et Skype pour les entreprises. Le compte est utilisé pour accéder à son calendrier de la réunion et établir Skype pour Business connectivity. Les utilisateurs peuvent réserver ce compte en planifiant une réunion à l’aide de celui-ci. Systèmes de salle Skype v2 sera en mesure de participer à cette réunion et fournir des fonctionnalités différentes aux participants à la réunion.
  
> [!IMPORTANT]
> Sans compte d’utilisateur, aucune des fonctionnalités ne peut fonctionner. 
  
Chaque compte d’utilisateur est unique à un seul périphérique v2 de systèmes de salle Skype et configurer :
  
- Le compte d’utilisateur doit être correctement configuré.
    
- Votre infrastructure doit être configuré pour permettre aux systèmes de salle Skype v2 pour valider le compte d’utilisateur et de joindre les services Microsoft appropriés.
    
> [!IMPORTANT]
> Il est vivement recommandé de créer ce compte bien avant l’installation effective du matériel. Si possible, la préparation du compte devrait commencer 2 à 3 semaines avant l’installation. 
  
Vous pouvez considérer un compte d’utilisateur que le compte personnes reconnaissent en tant que compte d’une conférence salle de réunion espace ou ressources. Lorsque vous souhaitez planifier une réunion qui se déroulera dans cette salle de réunion, vous invitez le compte à cette réunion. Pour pouvoir utiliser efficacement Skype salle systèmes v2, vous faire de même avec le compte d’utilisateur qui est affecté à chacune d’elles.
  
Si vous disposez déjà d’un compte de boîte aux lettres de ressources défini pour l’espace de réunion dans lequel vous installez Skype salle systèmes v2, vous pouvez modifier ce compte de ressource dans un compte d’utilisateur. Une fois cette opération effectuée, il vous souhaitez est ajouter le compte d’utilisateur pour un périphérique v2 de systèmes de salle Skype. Consultez les exemples de configuration de compte d’utilisateur fournis ci-après.
  
Avec une configuration supplémentaire, gestion à distance est possible à l’aide de la Suite de gestion des opérations Microsoft (OMS) comme décrit dans [Plan Skype salle v2 SMS avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [déployer Skype salle v2 SMS avec OMS](with-oms.md)et [gérer Périphériques v2 de systèmes de salle Skype avec OMS](../../manage/skype-room-systems-v2/oms.md). 
  
## <a name="basic-configuration"></a>Configuration de base

Ces propriétés représentent la configuration minimale pour un compte d’utilisateur travailler avec des systèmes de salle Skype v2. Votre compte d’utilisateur peut requérir une configuration supplémentaire.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Boîte aux lettres Exchange (Exchange 2013 SP1 ou version ultérieure, ou Exchange Online)  <br/> |Activation du compte avec une boîte aux lettres Exchange permet le compte d’utilisateur pour recevoir et envoyer des messages et demandes de réunion et afficher un calendrier des réunions sur l’appareil v2 de systèmes de salle Skype. La boîte aux lettres de systèmes de salle Skype v2 doit correspondre à une boîte aux lettres de salle.  <br/> |
|Skype pour les entreprises est activé.  <br/> |Skype pour les entreprises doit être activé pour pouvoir utiliser les diverses fonctionnalités de conférence, comme les appels vidéo, messagerie instantanée et le partage d’écran. Skype pour Business Online et Skype pour Business Server sont prises en charge.  <br/> |
|Activation par mot de passe  <br/> |Le compte d’utilisateur doit être activé par un mot de passe, ou il ne peut pas authentifier avec Exchange ou Skype pour Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuration avancée

Pendant les propriétés pour la configuration de base autorisera le compte d’utilisateur à être configurée dans un environnement simple, il est possible de votre environnement comporte d’autres restrictions sur les comptes de répertoire qui doivent être remplies pour systèmes de salle Skype v2 utiliser correctement le compte d’utilisateur.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Authentification basée sur un certificat  <br/> |Certificats peuvent être requis pour Exchange et Skype pour Business Server. Pour déployer les certificats, vous devez les charger lorsque vous vous connectez en tant qu’administrateur.  <br/> |
   
La meilleure façon de configurer des comptes d’utilisateur consiste à configurer à l’aide de Windows PowerShell à distance. Microsoft propose [SkypeRoomProvisioningScript.ps1](room-systems-v2-scripts.md), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles.
  
Si vous préférez utiliser l’interface utilisateur d’Office 365 sur les applets de commande Windows PowerShell, certaines étapes peuvent être effectuées manuellement. Consultez [Création d’un compte de périphérique à l’aide d’Office 365](https://technet.microsoft.com/itpro/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Voir aussi

#### 

[Planifier la salle Skype systèmes v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Configurer une console v2 de systèmes de salle de Skype](console.md)
  
[Gérer les salles Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


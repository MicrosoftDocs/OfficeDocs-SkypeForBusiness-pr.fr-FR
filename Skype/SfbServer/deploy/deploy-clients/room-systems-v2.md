---
title: Déploiement de Skype Room System v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cette rubrique pour en savoir plus sur les systèmes de salle Skype v2 et son intégration avec Exchange et Skype pour Business Server 2015.
ms.openlocfilehash: 54dc3d42d406fea2bdefcac5eb726dd77fde078f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2"></a>Déploiement de Skype Room System v2
 
Lisez cette rubrique pour en savoir plus sur les systèmes de salle Skype v2 et son intégration avec Exchange et Skype pour Business Server 2015.
  
Cette rubrique présente la création de comptes utilisés par v2 de systèmes de salle Skype dans Microsoft Exchange et Skype pour Business Server 2015. Instructions de déploiement pour les périphériques de systèmes de salle Skype v2 est couvert dans [configurer une console v2 de systèmes de salle de Skype](console.md). Votre infrastructure peut correspondre à l’une des configurations suivantes :
  
- Déploiement en ligne : votre environnement de déploiement entièrement sur Office 365. Pour plus d’informations, consultez [v2 de déployer des systèmes de salle Skype avec Office 365](with-office-365.md).
    
- Déploiement sur site : votre organisation dispose de serveurs qu’il contrôle, où sont hébergés les Skype pour Business Server 2015, Exchange et Active Directory. Pour plus d’informations, reportez-vous à la section [v2 de déployer des systèmes de salle Skype avec Skype pour Business Server 2015](with-skype-for-business-server-2015.md)
    
- Déploiement hybride : votre organisation possède un mélange de services, avec une partie hébergée sur locaux et certaines hébergées en ligne via Office 365. Avec les systèmes de salle Skype v2, les scénarios hybride suivants sont pris en charge : 
    
  - Exchange Online avec Skype pour 2015 de serveur d’entreprise dans les locaux. Pour plus d’informations, consultez [v2 de déployer des systèmes de salle Skype avec Exchange Online (hybride)](with-exchange-online.md).
    
  - Exchange sur site avec Skype pour entreprise en ligne. Pour plus d’informations, consultez [v2 de déployer des systèmes de salle Skype avec Exchange sur site (hybride)](with-exchange-on-premises.md).
    
La procédure de préparation de l’installation de l’appareil dépend de votre type de configuration.
  
Systèmes de salle Skype v2 doit être affecté à un compte d’utilisateur « » dans Active Directory, Exchange et Skype pour les entreprises. Le compte est utilisé pour accéder à son calendrier de réunion et établir Skype pour la connectivité de l’entreprise. Les utilisateurs peuvent réserver ce compte en planifiant une réunion à l’aide de celui-ci. Systèmes de salle Skype v2 sera en mesure de participer à cette réunion et offrent des fonctionnalités différentes pour les participants à la réunion.
  
> [!IMPORTANT]
> Sans compte d’utilisateur, aucune des fonctionnalités ne peut fonctionner. 
  
Chaque compte d’utilisateur est unique à un seul périphérique de v2 de systèmes de salle Skype et configurer :
  
- Le compte d’utilisateur doit être correctement configuré.
    
- Votre infrastructure doit être configuré pour autoriser les systèmes de salle Skype v2 pour valider le compte d’utilisateur et pour atteindre les services appropriés de Microsoft.
    
> [!IMPORTANT]
> Il est vivement recommandé de créer ce compte bien avant l’installation effective du matériel. Si possible, la préparation du compte devrait commencer 2 à 3 semaines avant l’installation. 
  
Vous pouvez considérer un compte d’utilisateur que le compte de ressources les utilisateurs peuvent-ils reconnaître en tant que compte d’une conférence de l’espace ou de réunion espace. Lorsque vous souhaitez planifier une réunion qui se déroulera dans cette salle de réunion, vous invitez le compte à cette réunion. Pour pouvoir utiliser Skype salle systèmes v2 plus efficacement, vous faites de même avec le compte d’utilisateur qui est affecté à chacun d’eux.
  
Si vous avez déjà un compte de boîte aux lettres de ressource définie pour l’espace de réunion où vous installez Skype salle systèmes v2, vous pouvez modifier ce compte de ressource dans un compte d’utilisateur. Une fois cette opération effectuée, vous devez faire est ajouter le compte d’utilisateur sur un périphérique de v2 de systèmes de salle de Skype. Consultez les exemples de configuration de compte d’utilisateur fournis ci-après.
  
Une configuration supplémentaire, l’administration à distance est possible à l’aide de Microsoft Operations Management Suite (OMS) comme décrit dans le [Plan Skype salle v2 SMS avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [déployer Skype salle v2 SMS avec OMS](with-oms.md)et [gérer Les périphériques systèmes de salle Skype v2 avec OMS](../../manage/skype-room-systems-v2/oms.md). 
  
## <a name="basic-configuration"></a>Configuration de base

Ces propriétés représentent la configuration minimale pour un compte d’utilisateur fonctionner avec les systèmes de salle Skype v2. Votre compte d’utilisateur peut requérir une configuration supplémentaire.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Boîte aux lettres Exchange (Exchange 2013 SP1 ou version ultérieure, ou Exchange en ligne)  <br/> |L’activation du compte avec une boîte aux lettres Exchange permet le compte d’utilisateur pour recevoir et envoyer des messages et des demandes de réunion et d’afficher un calendrier des réunions sur l’appareil v2 de systèmes de salle de Skype. La boîte aux lettres de systèmes de salle Skype v2 doit être une boîte aux lettres de salle.  <br/> |
|Skype pour entreprise est activé.  <br/> |Skype pour entreprise doit être activée pour pouvoir utiliser les diverses fonctionnalités de conférence, tels que les appels vidéo, la messagerie instantanée et le partage d’écran. À la fois Skype pour Business Online et Skype pour Business Server sont pris en charge.  <br/> |
|Activation par mot de passe  <br/> |Le compte d’utilisateur doit être activé avec un mot de passe, ou il ne peut pas s’authentifier avec Exchange ou Skype pour Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuration avancée

Lorsque les propriétés pour la configuration de base permettra le compte d’utilisateur à définir dans un environnement simple, il est possible de votre environnement comporte d’autres restrictions sur les comptes de répertoire qui doivent être remplies pour v2 Skype salle systèmes afin de pouvoir utiliser le compte d’utilisateur.
  
|**Propriété**|**Objectif**|
|:-----|:-----|
|Authentification basée sur un certificat  <br/> |Les certificats peuvent être requis pour Exchange et Skype pour Business Server. Pour déployer les certificats, vous devez les charger lorsque vous vous connectez en tant qu’administrateur.  <br/> |
   
La meilleure façon de configurer des comptes d’utilisateur doit les configurer à l’aide d’à distance de Windows PowerShell. [Microsoft propose des scripts](https://go.microsoft.com/fwlink/?linkid=870105) qui vous aideront à créer de nouveaux comptes d’utilisateur, ou de valider les comptes de ressource existant dont vous disposez pour vous aider à les transformer en comptes d’utilisateurs de v2 Skype salle systèmes compatibles.
  
Si vous préférez utiliser l’interface utilisateur de Office 365 sur les applets de commande Windows PowerShell, certaines étapes peuvent être effectuées manuellement. Reportez-vous à la section [Création d’un compte de périphérique à l’aide d’Office 365](https://technet.microsoft.com/en-us/itpro/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Voir aussi

#### 

[Plan de salle de Skype systèmes v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Configurer une console v2 de systèmes de salle de Skype](console.md)
  
[Gérer l’espace de Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


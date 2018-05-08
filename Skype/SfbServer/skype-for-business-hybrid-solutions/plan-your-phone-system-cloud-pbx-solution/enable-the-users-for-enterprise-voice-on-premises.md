---
title: Activer les utilisateurs pour Enterprise Voice sur site
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Pour un utilisateur à utiliser le système téléphonique dans Office 365 (en nuage PBX), vous devez tout d’abord les activer pour Enterprise Voice et affecter un numéro de téléphone. Cela à l’aide de votre déploiement sur site pendant que l’utilisateur est toujours hébergé dans le déploiement local.
ms.openlocfilehash: 1099aa825d76017df3afe64cf6d7b3c39391a883
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Activer les utilisateurs pour Enterprise Voice sur site
 
Pour un utilisateur à utiliser le système téléphonique dans Office 365 (en nuage PBX), vous devez tout d’abord les activer pour Enterprise Voice et affecter un numéro de téléphone. Cela à l’aide de votre déploiement sur site pendant que l’utilisateur est toujours hébergé dans le déploiement local.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Pour activer un utilisateur pour Enterprise Voice sur site et affecter un numéro de téléphone

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Utilisez le menu Démarrer ou le raccourci bureau pour ouvrir le Panneau de configuration de Skype Entreprise Server.
    
    Vous pouvez également ouvrir une fenêtre de navigateur, puis saisir l’URL de l’administrateur pour ouvrir le Panneau de configuration de Skype Entreprise Server
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le Skype Business en ligne compte d’utilisateur que vous souhaitez activer pour Enterprise Voice.
    
6. Dans le menu **Modifier**, cliquez sur **Afficher les détails**.
    
7. Sous **Téléphonie**, cliquez sur **Voix Entreprise**.
    
8. Cliquez sur l’**URI de ligne**, puis saisissez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200). Ensuite, cliquez sur **Valider**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considérations particulières lors de l’activation des utilisateurs pour Enterprise Voice sur site

Dans certains cas, vous devrez peut-être modifier la façon d’activer les utilisateurs pour Voix Entreprise de sorte qu’ils puissent passer et recevoir des appels de manière appropriée. Si vous avez des utilisateurs qui répondent aux conditions suivantes dans votre déploiement, effectuez les étapes incluses pour permettre à l’utilisateur pour Enterprise Voice.
  
- Si un utilisateur est créé dans votre environnement local AD synchronisé avec Skype pour Business Online sans être activé pour Skype pour les entreprises ou pour Enterprise Voice et n’ont pas LineURI définir, exécutez les applets de commande suivantes pour chaque utilisateur concerné, en remplaçant les valeurs < C0 > <b1></b1> par des valeurs réelles pour votre environnement :
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé pour Skype pour les entreprises dans les locaux, mais a été pas activé pour Enterprise Voice ou affecté LineURI avant d’être déplacés à Skype pour Business Online, exécutez l’applet de commande suivante pour chaque utilisateur :
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé dans Skype pour les entreprises dans les locaux, mais pas activé pour Enterprise Voice, même si déjà affecté un LineURI, exécutez la cmdlet suivante pour chaque utilisateur affecté :
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```



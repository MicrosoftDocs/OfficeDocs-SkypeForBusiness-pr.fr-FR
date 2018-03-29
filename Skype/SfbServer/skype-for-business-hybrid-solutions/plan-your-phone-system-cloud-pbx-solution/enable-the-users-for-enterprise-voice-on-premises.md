---
title: Permettre aux utilisateurs de Voix Entreprise dans les locaux
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Pour un utilisateur d’utiliser le système téléphonique dans Office 365 (PBX Cloud), vous devez tout d’abord les activer pour Voix Entreprise et affecter un numéro de téléphone. Cela à l’aide de votre déploiement sur site pendant que l’utilisateur est toujours hébergée dans le déploiement sur site.
ms.openlocfilehash: c661d6da46cc42843346541b29841a728ab0fc16
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Permettre aux utilisateurs de Voix Entreprise dans les locaux
 
Pour un utilisateur d’utiliser le système téléphonique dans Office 365 (PBX Cloud), vous devez tout d’abord les activer pour Voix Entreprise et affecter un numéro de téléphone. Cela à l’aide de votre déploiement sur site pendant que l’utilisateur est toujours hébergée dans le déploiement sur site.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Pour permettre à un utilisateur de Voix Entreprise dans les locaux et affecter un numéro de téléphone

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Utilisez le menu Démarrer ou le raccourci bureau pour ouvrir le Panneau de configuration de Skype Entreprise Server.
    
    Vous pouvez également ouvrir une fenêtre de navigateur, puis saisir l’URL de l’administrateur pour ouvrir le Panneau de configuration de Skype Entreprise Server
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le Skype Business Online compte d’utilisateur que vous souhaitez activer pour les Voix Entreprise.
    
6. Dans le menu **Modifier**, cliquez sur **Afficher les détails**.
    
7. Sous **Téléphonie**, cliquez sur **Voix Entreprise**.
    
8. Cliquez sur l’**URI de ligne**, puis saisissez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200). Ensuite, cliquez sur **Valider**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considérations lors de l’activation des utilisateurs pour les Voix Entreprise dans les locaux

Dans certains cas, vous devrez peut-être modifier la façon d’activer les utilisateurs pour Voix Entreprise de sorte qu’ils puissent passer et recevoir des appels de manière appropriée. Si vous avez des utilisateurs qui remplissent les conditions suivantes dans votre déploiement, exécutez les étapes incluses pour permettre à l’utilisateur de Voix Entreprise.
  
- Si un utilisateur est créé dans vos locaux AD et ensuite synchronisés avec Skype pour professionnels en ligne sans être activé pour Skype pour entreprise ou pour la Voix Entreprise et n’ont pas une LineURI définir, exécuter les applets de commande suivantes pour chaque utilisateur concerné, en remplaçant les valeurs de < C0 > <b1></b1> par des valeurs réelles pour votre environnement :
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé pour Skype pour les entreprises dans les locaux, mais a été pas activé pour les Voix Entreprise ou affecté un LineURI avant d’être déplacés à Skype pour Business Online, exécutez l’applet de commande suivante pour chaque utilisateur :
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé dans Skype pour les entreprises dans les locaux mais pas activé pour les Voix Entreprise, même si déjà attribué un LineURI, exécutez l’applet de commande suivante pour chaque utilisateur concerné :
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```



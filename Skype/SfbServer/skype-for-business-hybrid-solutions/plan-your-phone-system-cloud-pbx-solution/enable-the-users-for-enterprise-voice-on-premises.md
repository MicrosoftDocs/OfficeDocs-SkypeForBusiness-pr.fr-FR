---
title: Permettre aux utilisateurs d’utiliser la voix entreprise en local
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Pour qu’un utilisateur utilise le système téléphonique dans Office 365 (PBX Cloud), vous devez d’abord l’activer pour voix entreprise et lui attribuer un numéro de téléphone. Pour ce faire, vous devez utiliser votre déploiement local alors que l’utilisateur est toujours hébergé dans le déploiement local.
ms.openlocfilehash: fdd405d84cddcfe805063287b8330ccea43397de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287509"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Permettre aux utilisateurs d’utiliser la voix entreprise en local
 
Pour qu’un utilisateur utilise le système téléphonique dans Office 365 (PBX Cloud), vous devez d’abord l’activer pour voix entreprise et lui attribuer un numéro de téléphone. Pour ce faire, vous devez utiliser votre déploiement local alors que l’utilisateur est toujours hébergé dans le déploiement local.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Pour permettre à un utilisateur d’utiliser la voix entreprise sur site et d’affecter un numéro de téléphone

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Utilisez le menu Démarrer ou le raccourci bureau pour ouvrir le Panneau de configuration de Skype Entreprise Server.
    
    Vous pouvez également ouvrir une fenêtre de navigateur, puis saisir l’URL de l’administrateur pour ouvrir le Panneau de configuration de Skype Entreprise Server
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur Skype entreprise Online que vous voulez activer pour voix entreprise.
    
6. Dans le menu **Modifier**, cliquez sur **Afficher les détails**.
    
7. Sous **Téléphonie**, cliquez sur **Voix Entreprise**.
    
8. Cliquez sur l’**URI de ligne**, puis saisissez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200). Ensuite, cliquez sur **Valider**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Remarques spéciales lors de l’activation de la voix entreprise locale dans les utilisateurs

Dans certains cas, vous devrez peut-être modifier la façon d’activer les utilisateurs pour Voix Entreprise de sorte qu’ils puissent passer et recevoir des appels de manière appropriée. Si votre déploiement comporte des utilisateurs qui répondent aux conditions suivantes, suivez les étapes décrites dans la procédure d’activation de l’utilisateur pour voix entreprise.
  
- Si un utilisateur est créé dans votre annonce locale et qu’elle est synchronisée avec Skype entreprise Online sans être activée pour Skype entreprise ou pour Enterprise Voice et ne disposant pas d’un LineURI, exécutez les applets de commande suivantes pour chaque utilisateur concerné, en remplaçant les valeurs de < C0 > <b1></b1> avec des valeurs réelles pour votre environnement:
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé pour Skype entreprise en local, mais qu’il n’a pas été activé pour voix entreprise ou qu’il n’a pas été affecté à une LineURI avant d’être déplacé dans Skype entreprise Online, exécutez l’applet de commande suivante pour chaque utilisateur:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé dans Skype entreprise sur site, mais n’est pas activé pour voix entreprise, même s’il a déjà reçu une LineURI, exécutez l’applet de commande suivante pour chaque utilisateur concerné:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```



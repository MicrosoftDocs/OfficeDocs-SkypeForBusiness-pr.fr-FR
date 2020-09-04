---
title: Activer les utilisateurs pour voix entreprise sur site
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Pour qu’un utilisateur utilise le système téléphonique (PBX Cloud), vous devez d’abord l’activer pour voix entreprise et lui attribuer un numéro de téléphone. Pour ce faire, utilisez votre déploiement local pendant que l’utilisateur est toujours hébergé dans le déploiement local.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359190"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Activer les utilisateurs pour voix entreprise sur site
 
Pour qu’un utilisateur utilise le système téléphonique (PBX Cloud), vous devez d’abord l’activer pour voix entreprise et lui attribuer un numéro de téléphone. Pour ce faire, utilisez votre déploiement local pendant que l’utilisateur est toujours hébergé dans le déploiement local.

> [!Important]
> Skype entreprise Online sera supprimé le 31 juillet 2021 après lequel le service ne sera plus accessible.  De plus, la connectivité PSTN entre votre environnement local, que ce soit via Skype entreprise Server ou Cloud Connector Edition et Skype entreprise Online, ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Pour activer un utilisateur pour voix entreprise sur site et attribuer un numéro de téléphone

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Utilisez le menu Démarrer ou le raccourci Bureau pour ouvrir le panneau de configuration de Skype entreprise Server.
    
    Vous pouvez également ouvrir une fenêtre de navigateur, puis entrer l’URL de l’administrateur pour ouvrir le panneau de configuration de Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur Skype entreprise Online que vous souhaitez activer pour voix entreprise.
    
6. Dans le menu **Edition** , cliquez sur **afficher les détails**.
    
7. Sous **téléphonie**, cliquez sur **voix entreprise**.
    
8. Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tel : + 14255550200). Ensuite, cliquez sur **valider**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considérations particulières lors de l’activation des utilisateurs pour voix entreprise sur site

Dans certains cas, vous devrez peut-être modifier la façon dont vous activez les utilisateurs pour voix entreprise afin de vous assurer qu’ils peuvent passer et recevoir des appels. Si des utilisateurs de votre déploiement remplissent les conditions suivantes, effectuez les étapes requises pour activer l’utilisateur pour voix entreprise.
  
- Si un utilisateur est créé dans votre AD sur site, puis synchronisé avec Skype entreprise Online sans être activé pour Skype entreprise ou pour voix entreprise et n’ont pas de jeu LineURI, exécutez les applets de commande suivantes pour chaque utilisateur affecté, en remplaçant les valeurs par les \< \> valeurs réelles de votre environnement :
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé pour Skype entreprise en local, mais n’a pas été activé pour voix entreprise ou s’il a été affecté à un LineURI avant d’être déplacé vers Skype entreprise Online, exécutez l’applet de commande suivante pour chaque utilisateur :
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé dans Skype entreprise en local, mais n’est pas activé pour voix entreprise, même si un LineURI a déjà été affecté, exécutez l’applet de commande suivante pour chaque utilisateur concerné :
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```



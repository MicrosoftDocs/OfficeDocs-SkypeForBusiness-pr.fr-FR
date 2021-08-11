---
title: Activer les utilisateurs pour Voix Entreprise local
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
description: Pour qu’un utilisateur utilise Système téléphonique (CLOUD PBX), vous devez d’abord l’activer pour Voix Entreprise et lui attribuer un numéro de téléphone. Pour ce faire, utilisez votre déploiement local alors que l’utilisateur est toujours dos au déploiement local.
ms.openlocfilehash: aef74877d1a12d136bddc7eedc2a414dfad100830a88bb9a21695004be91d1a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289082"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Activer les utilisateurs pour Voix Entreprise local
 
Pour qu’un utilisateur utilise Système téléphonique (CLOUD PBX), vous devez d’abord l’activer pour Voix Entreprise et lui attribuer un numéro de téléphone. Pour ce faire, utilisez votre déploiement local alors que l’utilisateur est toujours dos au déploiement local.

> [!Important]
> Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.  En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Pour activer un utilisateur pour Voix Entreprise local et affecter un numéro de téléphone

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Utilisez le raccourci menu Démarrer bureau ou de bureau pour ouvrir Skype Entreprise Server panneau de Skype Entreprise Server de contrôle.
    
    Vous pouvez également ouvrir une fenêtre de navigateur, puis entrer l’URL de l’administrateur pour ouvrir Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d Skype Entreprise Online que vous souhaitez activer pour Voix Entreprise.
    
6. Dans le menu **Edition,** cliquez **sur Afficher les détails.**
    
7. Sous **Téléphonie,** cliquez sur **Voix Entreprise**.
    
8. Cliquez **sur URI** de ligne et tapez un numéro de téléphone unique et normal (par exemple, tel:+14255550200). Cliquez ensuite sur **Valider.**
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considérations spéciales lors de l’activation des utilisateurs Voix Entreprise sur site

Dans certains cas, vous devrez peut-être modifier la façon dont vous activez les utilisateurs pour Voix Entreprise pour vous assurer qu’ils peuvent effectuer et recevoir des appels. Si votre déploiement compte des utilisateurs qui répondent aux conditions suivantes, effectuez les étapes incluses pour activer l’utilisateur pour Voix Entreprise.
  
- Si un utilisateur est créé dans votre AD local, puis synchronisé avec Skype Entreprise Online sans être activé pour Skype Entreprise ou pour Voix Entreprise et que vous n’avez pas de lineURI, exécutez les cmdlets suivantes pour chaque utilisateur concerné, en remplaçant les valeurs par les valeurs réelles de votre environnement \< \> :
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé pour Skype Entreprise en local, mais qu’il n’a pas été activé pour Voix Entreprise ou si un LineURI lui a été affecté avant d’être déplacé vers Skype Entreprise Online, exécutez l’cmdlet suivante pour chaque utilisateur :
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un utilisateur est déjà activé dans Skype Entreprise sur site, mais pas pour Voix Entreprise, même s’il a déjà affecté un LineURI, exécutez l’cmdlet suivante pour chaque utilisateur concerné :
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```
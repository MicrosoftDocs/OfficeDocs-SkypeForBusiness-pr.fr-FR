---
title: Configurer des clauses d’exclusion de responsabilité d’archivage pour les utilisateurs externes dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer une clause d’exclusion de responsabilité d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: 05eaec40556b383525331405463ee6d0a10e0a13
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834712"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurer des clauses d’exclusion de responsabilité d’archivage pour les utilisateurs externes dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer une clause d’exclusion de responsabilité d’archivage pour Skype Entreprise Server.
  
Si votre organisation communique avec des partenaires externes, vous devez leur faire savoir que vous archivez les communications avec eux. Lorsque vous déployez un serveur Edge et activez la fédération pour votre organisation, vous êtes invité à envoyer automatiquement une clause d’exclusion de responsabilité d’archivage à des partenaires externes. 
  
Si vous devez modifier cette configuration, vous pouvez utiliser le Panneau de configuration Skype Entreprise Server ou l’Windows PowerShell cmdlet **Set-CsAccessEdgeConfiguration.** Les cmdlets peuvent être exécutés à partir de l’Skype Entreprise Server de gestion ou d’une session distante de Windows PowerShell.
  
Pour permettre aux utilisateurs externes de collaborer avec des utilisateurs dans votre déploiement Skype Entreprise Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs externes. Pour plus d’informations, voir Manage XMPP Federated Partners for Your Organization. Pour plus d’informations sur le contrôle d’accès pour des domaines fédérés spécifiques, voir Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Activer ou désactiver la clause d’exclusion de responsabilité d’archivage à l’aide du Panneau de contrôle

1. Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.
    
4. Dans l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.
    
5. Dans Modifier la **configuration** du edge d’accès, sous  Activer la fédération et la connectivité **DE** messagerie instantanée publique, activez ou désactivez la case à cocher Envoyer la clause d’exclusion de responsabilité d’archivage aux partenaires fédérés pour activer ou désactiver l’envoi automatique de la clause d’exclusion de responsabilité d’archivage.
    
6. Cliquez sur **Valider**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Activer ou désactiver la clause d’exclusion de responsabilité d’archivage à l’aide Windows PowerShell

Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```



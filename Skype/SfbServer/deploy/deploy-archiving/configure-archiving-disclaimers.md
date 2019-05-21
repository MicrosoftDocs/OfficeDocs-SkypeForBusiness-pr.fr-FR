---
title: Configuration de l’archivage des demandes d’incentive pour les utilisateurs externes dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Résumé: cette rubrique vous explique comment configurer un déni d’utilisation de l’archivage pour Skype entreprise Server.'
ms.openlocfilehash: 86430ac80d85ed166ae091119f4261cdc5e1ff9b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278982"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configuration de l’archivage des demandes d’incentive pour les utilisateurs externes dans Skype entreprise Server
 
**Résumé:** Pour plus d’informations sur la configuration d’un déni d’utilisation pour Skype entreprise Server, reportez-vous à cette rubrique.
  
Si votre organisation communique avec des partenaires externes, vous devez leur faire savoir que vous archivez vos communications. Lorsque vous déployez un serveur Edge et activez la Fédération pour votre organisation, vous êtes invité à indiquer si vous souhaitez envoyer automatiquement une exclusion d’autorisation à des partenaires externes. 
  
Si vous devez modifier cette configuration, vous pouvez utiliser le panneau de configuration Skype entreprise Server ou l’applet de commande Windows PowerShell **Set-CsAccessEdgeConfiguration** . Les applets de commande peuvent être exécutées à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.
  
Pour permettre aux utilisateurs externes de collaborer avec des utilisateurs dans le déploiement de Skype entreprise Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs externes. Pour plus d’informations, reportez-vous à la rubrique gérer les partenaires fédérés fédérés pour votre organisation. Pour plus d’informations sur le contrôle d’accès de domaines fédérés spécifiques, reportez-vous à Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Activer ou désactiver une nouvelle notification d’exclusion relative à l’archivage à l’aide du panneau de configuration

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.
    
4. Sous l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la configuration du serveur Edge d’accès**, sous **Activer la fédération et la connectivité PIC**, activez ou désactivez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage** pour activer ou désactiver l’envoi automatique d’une notification d’exclusion relative à l’archivage.
    
6. Cliquez sur **Valider**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Activer ou désactiver une nouvelle notification d’exclusion relative à l’archivage à l’aide de Windows PowerShell

Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```



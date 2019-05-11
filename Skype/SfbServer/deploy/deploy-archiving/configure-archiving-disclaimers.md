---
title: Configurer des notifications d’exclusion d’archivage pour les utilisateurs externes Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer une notification d’exclusion d’archivage pour Skype pour Business Server.'
ms.openlocfilehash: 7cc1c5c770a20c9ccd4d1473eeca4147042fde95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894154"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurer des notifications d’exclusion d’archivage pour les utilisateurs externes Skype pour Business Server
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer une notification d’exclusion d’archivage pour Skype pour Business Server.
  
Si votre organisation communique avec des partenaires externes, vous devez leur faire savoir que vous archivez vos communications. Lorsque vous déployez un serveur de périphérie et activez la fédération pour votre organisation, vous êtes invité si vous souhaitez envoyer automatiquement une notification d’exclusion d’archivage aux partenaires externes. 
  
Si vous devez modifier cette configuration, vous pouvez utiliser la Skype pour le panneau de configuration serveur Business ou l’applet de commande Windows PowerShell **Set-CsAccessEdgeConfiguration** . Applets de commande peut être exécutée à partir de la Skype pour le shell de gestion Business Server ou à partir d’une session à distance de Windows PowerShell.
  
Pour permettre aux utilisateurs externes de collaborer avec des utilisateurs dans votre Skype pour le déploiement de serveur d’entreprise, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs externes. Pour plus d’informations, voir Manage XMPP Federated Partners for Your Organization. Pour plus d’informations sur le contrôle d’accès de domaines fédérés spécifiques, reportez-vous à Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Activer ou désactiver une nouvelle notification d’exclusion relative à l’archivage à l’aide du panneau de configuration

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
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



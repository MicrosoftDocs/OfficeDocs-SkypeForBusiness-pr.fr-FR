---
title: Configuration des notifications d’exclusion relatives à l’archivage pour les utilisateurs externes dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer une exclusion de responsabilité d’archivage pour Skype pour Business Server 2015.'
ms.openlocfilehash: 3790160024010084c69df7d9865f17622fca4f0d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server-2015"></a>Configuration des notifications d’exclusion relatives à l’archivage pour les utilisateurs externes dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer une exclusion de responsabilité d’archivage pour Skype pour Business Server 2015.
  
Si votre organisation communique avec des partenaires externes, vous devez leur faire savoir que vous archivez vos communications. Lorsque vous déployez un serveur de transport Edge et activez la fédération pour votre organisation, vous êtes invité si vous souhaitez envoyer automatiquement une décharge de responsabilité d’archivage pour les partenaires externes. 
  
Si vous avez besoin de modifier cette configuration, vous pouvez utiliser le Skype pour Business Server du Panneau de configuration ou l’applet de commande Windows PowerShell **Set-CsAccessEdgeConfiguration** . Applets de commande peut être exécuté à partir de la Skype pour le shell de gestion Business Server ou à partir d’une session à distance de Windows PowerShell.
  
Pour permettre aux utilisateurs externes de collaborer avec des utilisateurs dans votre Skype pour le déploiement du serveur de l’entreprise, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge les accès des utilisateurs externes. Pour plus d’informations, voir gérer les partenaires fédérés XMPP pour votre organisation. Pour plus d’informations sur le contrôle d’accès de domaines fédérés spécifiques, reportez-vous à Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Activer ou désactiver une nouvelle notification d’exclusion relative à l’archivage à l’aide du panneau de configuration

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
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



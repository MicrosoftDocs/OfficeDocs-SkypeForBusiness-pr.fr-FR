---
title: "Activer la diffusion de réunion Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Que les personnes de votre organisation puissent utiliser la diffusion de réunion Skype, vous devez l’activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne connaissez pas Windows PowerShell, songez à faire appel à un partenaire de Microsoft d’effectuer cette étape pour vous."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a>Activer la diffusion de réunion Skype

Que les personnes de votre organisation puissent utiliser la diffusion de réunion Skype, vous devez l’activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne connaissez pas Windows PowerShell, envisager d’engager un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) d’effectuer cette étape pour vous.
  
> [!CAUTION]
> Diffusion de réunion Skype est désactivée par défaut car la distribution du contenu multimédia d’une réunion de diffusion utilise un réseau de livraison de contenu (CDN de Microsoft Azure) pour atteindre une échelle très élevée pour la prise en charge des milliers de personnes Assistant à une diffusion. Le contenu du média mémorisé en bloc passant par le CDN est crypté, et le cache CDN a une durée de vie limitée. En outre, le composant Azure CDN ne répondent pas encore aux tous les éléments des Clauses de modèle de l’Union européenne qui découlent de la Directive de Protection des données de l’Union européenne. En activant cette fonctionnalité, vous reconnaissez cet avis. 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Activer la diffusion de réunion Skype à l’aide de la Skype pour le centre d’administration Business

1. Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. Dans le centre d’administration d’Office 365, accédez au **Centre d’administration** > **Skype pour les entreprises**.
    
3. Dans le **Skype pour Business admin center**, accédez à **des réunions en ligne** > **réunions de diffusion**, puis sélectionnez **Activer la diffusion de réunion Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Activer la diffusion de réunion Skype à l’aide de PowerShell

1. Vérifiez que vous exécutez la version 3.0 ou ultérieure de Windows PowerShell.
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
2. Dans le **Menu Démarrer**, choisissez **Windows PowerShell**.
    
3. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. Vérifiez votre configuration en cours de diffusion de réunion Skype en exécutant :
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Vérifiez que le paramètre _EnableBroadcastMeeting_ est défini sur `False`.
    
     ![Applet de commande Skype réunion de diffusion activer l’organisation.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Activer la diffusion de réunion Skype pour votre organisation en exécutant :
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Vous pouvez vérifier que le paramètre est activé en exécutant `Get-CsBroadcastMeetingConfiguration` à nouveau.
    
     ![Activer de la Cmdlet de l’organisation de la diffusion de réunion Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Après avoir apporté la modification, il peut prendre une heure soient prises en compte dans le portail de diffusion de réunion Skype. 
  
6. Vos utilisateurs peuvent maintenant organiser des réunions de diffusion avec d’autres utilisateurs dans votre entreprise. Pour obtenir leur démarrage, les pointer vers [ce qu’est une diffusion de réunion Skype ?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurez votre réseau pour la diffusion des réunions avec des participants externes

Si vous disposez d’un pare-feu et que vous souhaitez avoir des diffusions avec des personnes en dehors de votre entreprise (qui ne sont pas une entreprise fédérée), vous devez configurer votre réseau à l’aide de ces instructions : [configurer votre réseau de diffusion de réunion Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si vous n’êtes pas familiarisé avec la configuration de votre pare-feu, envisager d’engager un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) d’effectuer cette étape pour vous.
  
Pour ignorer cette étape et l’ajouter à la place d’une autre entreprise de votre fédération, reportez-vous à la section [Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Rubriques connexes

[Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)


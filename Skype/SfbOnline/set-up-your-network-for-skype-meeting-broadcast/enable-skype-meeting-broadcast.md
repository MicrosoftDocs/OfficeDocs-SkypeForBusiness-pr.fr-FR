---
title: Activer une diffusion de réunion Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Pour que les membres de votre organisation peuvent utiliser la diffusion de réunion Skype, vous devez l’activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne connaissez pas l’Windows PowerShell, envisagez de faire appel à un partenaire Microsoft pour faire cette étape pour vous.
ms.openlocfilehash: 1ba8f11913c932d695806ae4fd30db5e8609530f
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865138"
---
# <a name="enable-skype-meeting-broadcast"></a>Activer une diffusion de réunion Skype

> [!IMPORTANT]
> Skype Entreprise Online prend fin le 31 juillet 2021, date à laquelle l’accès au service prendra fin. Nous encourageons les clients à commencer la mise à niveau vers Microsoft Teams, le client principal pour les communications et le travail d’équipe dans Microsoft 365.

Pour que les membres de votre organisation peuvent utiliser la diffusion de réunion Skype, vous devez l’activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne connaissez pas Windows PowerShell, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.



> [!NOTE]
> Le Centre d’administration Microsoft Teams a remplacé le Centre d’administration Skype Entreprise (portail hérité). Tous les paramètres de gestion de Skype Entreprise sont désormais dans le Centre d’administration Teams. Pour gérer les fonctionnalités de Skype Entreprise dans le Centre d’administration Teams, vous devez avoir le rôle d’administrateur [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) d’administrateur global ou d’administrateur Skype Entreprise. Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Activer la diffusion de réunion Skype au moyen du Centre d'administration de Skype Entreprise

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

1. Connectez-vous à l’adresse : votre compte d’administrateur global ou votre compte d’administrateur Skype [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) Entreprise.
    
2. Dans le Centre d’administration, allez dans Centres **d’administration**  >  **Teams.**
    
3. Dans le Centre **d’administration Teams,** sélectionnez **Diffusion** de réunion via le portail hérité, puis sélectionnez Activer la diffusion  >    >  de **réunion Skype.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Activer la diffusion de réunion Skype avec PowerShell

1. Vérifiez que vous exécutez la version 3.0 ou supérieure de Windows PowerShell.
    
2. Pour vérifier que vous exécutez la version 3.0 ou supérieure : cliquez sur **Démarrer** > **Windows PowerShell**.
    
3. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
4. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Voir [Windows Management Framework 4.0 pour](https://go.microsoft.com/fwlink/?LinkId=716845) télécharger et mettre à Windows PowerShell jour vers la version 4.0. Redémarrez votre ordinateur lorsque vous y êtes invité.
    
5. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
6. Dans le **menu Démarrer,** sélectionnez **Windows PowerShell.**
    
7. Dans la **Windows PowerShell,** connectez-vous à votre Microsoft 365 ou Office 365 en exécutant :
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Confirmez votre configuration Diffusion de réunion Skype actuelle en exécutant :
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Vérifiez que le paramètre  _EnableBroadcastMeeting_ est défini sur `False`.
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Activez Diffusion de réunion Skype pour votre organisation en exécutant :
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Vous pouvez vérifier que le paramètre est activé en le exécutant  `Get-CsBroadcastMeetingConfiguration` à nouveau.
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Une fois la modification effectuée, sa prise en compte sur le portail Diffusion de réunion Skype peut prendre jusqu'à une heure. 
  
10. Vos utilisateurs peuvent à présent organiser des réunions diffusées avec d'autres utilisateurs dans votre entreprise. Pour commencer, dirigez-les vers [Qu'est-ce qu'une diffusion de réunion Skype ?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d).
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurer votre réseau pour la diffusion de réunions à des participants externes

Si vous avez un pare-feu, et que vous souhaitez héberger des diffusions pour des personnes extérieures à votre entreprise (qui n'est pas une entreprise fédérée), vous devez configurer votre réseau avec les instructions suivantes : [Configurer votre réseau pour la Diffusion de réunion Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.
  
Pour ignorer cette étape et ajouter une autre entreprise à votre fédération, consultez [Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Sujets associés

[Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 

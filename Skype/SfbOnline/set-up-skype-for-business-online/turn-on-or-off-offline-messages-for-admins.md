---
title: Activation ou désactivation des messages hors connexion pour les administrateurs
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814603"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Activation ou désactivation des messages hors connexion pour les administrateurs

Vous pouvez envoyer des messages iM Skype Entreprise à vos contacts même s’ils ne sont pas encore inscrits. Cette fonctionnalité permet à vos contacts de savoir que vous avez essayé de les joindre. Vous n’avez pas à attendre qu’une personne soit en ligne pour lui envoyer un message.

Pour les messages hors connexion, il est important de savoir que :

- les messages hors connexion ne seront archivés dans la boîte aux lettres de l'utilisateur ;

- Les messages hors connexion seront envoyés vers la boîte aux lettres de l’utilisateur et seront avertis lorsqu’il se connectera à Skype Entreprise.

- Si le statut du destinataire  du message est Ne pas déranger ou En **présentation,** il reçoit un message manqué envoyé par le client Skype Entreprise du destinataire.

Pour plus d’informations, [voir Utiliser la messagerie hors connexion dans Skype Entreprise.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>Pour commencer

## #

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**

1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.

2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.

3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Voir [Windows Management Framework 4.0 pour](https://go.microsoft.com/fwlink/?LinkId=716845) télécharger et mettre à jour Windows PowerShell vers la version 4.0. Redémarrez votre ordinateur lorsque vous y êtes invité.

4. Vous devrez également installer le module Windows PowerShell teams qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online.

Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

## #

 **Démarrez une session Windows PowerShell**

1. From the **Start Menu** > **Windows PowerShell**.

2. Dans la **Windows PowerShell,** connectez-vous à votre Microsoft 365 ou Office 365 en exécutant :

   > [!NOTE]
   > Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.
   >
   > Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Pour plus d’informations sur le démarrage d Windows PowerShell, voir Se connecter à tous les [services Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>Activation ou désactivation de la messagerie instantanée hors connexion

> [!NOTE]
> Les messages  hors connexion ne sont disponibles que dans la dernière version du client Skype Entreprise « À exécuter en un clic » et ne le sont pas lorsqu’un ancien fichier Skype Entreprise « À exécuter en un clic » est utilisé ou qu’un fichier *.msi a été utilisé pour installer le client Skype Entreprise.

Pour activer ou désactiver l’envoi de messages hors connexion aux utilisateurs de votre organisation, définissez  _EnableIMAutoArchiving sur_ `True` ou `False` . Par défaut, cette option est définie sur `True` .

Pour éteindre, utilisez la cmdlet **Set-CsClientPolicy** et exécutez :

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Pour activer ou désactiver l’envoi de messages hors connexion à un utilisateur, définissez  _EnableIMAutoArchiving sur_ `True` `False` ou. Par défaut, cette option est définie sur  `True`. Vous pouvez utiliser une stratégie existante ou en créer une comme dans l’exemple ci-dessous.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Voir aussi
[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)



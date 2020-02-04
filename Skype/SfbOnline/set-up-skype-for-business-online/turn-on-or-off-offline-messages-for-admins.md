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
ms.openlocfilehash: 2b9cea6e7a4bcb3f7fc34bdf67e77353412d9e13
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706309"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Activation ou désactivation des messages hors connexion pour les administrateurs

Vous pouvez envoyer des messages instantanés Skype entreprise à vos contacts même s’ils ne sont pas connectés. Cette fonctionnalité permet à vos contacts de savoir que vous avez essayé d’y accéder. Vous n’avez pas besoin d’attendre qu’une personne reste en ligne avant de lui envoyer un message.

Pour les messages hors connexion, il est important de savoir que :

- les messages hors connexion ne seront archivés dans la boîte aux lettres de l'utilisateur ;

- Les messages hors connexion seront envoyés dans la boîte aux lettres de l’utilisateur, et l’utilisateur est averti dès qu’il se connecte à Skype entreprise.

- Si le statut du destinataire du message est défini sur **ne pas déranger** ou en **Présentation**, il recevra un message manqué, envoyé par le client Skype entreprise du destinataire.

Pour plus d’informations, reportez-vous à la rubrique [utilisation de la messagerie hors connexion dans Skype entreprise](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Pour commencer

## #

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**

1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.

2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.

3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.

4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.

Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

## #

 **Démarrez une session Windows PowerShell**

1. From the **Start Menu** > **Windows PowerShell**.

2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :

    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

## <a name="turning-on-or-off-offline-im"></a>Activation ou désactivation de la messagerie instantanée hors connexion

> [!NOTE]
> Les messages hors connexion ne sont disponibles **que** dans la dernière version du client « démarrer en un clic » de Skype entreprise et ne sont pas disponibles lorsqu’une version antérieure de Skype entreprise est utilisée ou qu’un fichier *. msi a été utilisé pour installer le client Skype entreprise.

Pour activer ou désactiver les messages hors connexion pour les utilisateurs de votre organisation qui envoient `True` des `False`messages hors connexion, définissez _EnableIMAutoArchiving_ sur ou. Par défaut, ce paramètre est défini `True`sur.

Pour éteindre, utilisez la cmdlet **Set-CsClientPolicy** et exécutez :

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Pour activer ou désactiver les messages hors connexion pour les utilisateurs qui envoient des `True` messages `False`hors connexion, définissez _EnableIMAutoArchiving_ sur ou. Par défaut, cette option est définie sur  `True`. Vous pouvez utiliser une stratégie existante ou en créer une comme dans l’exemple ci-dessous.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Six raisons d’utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)



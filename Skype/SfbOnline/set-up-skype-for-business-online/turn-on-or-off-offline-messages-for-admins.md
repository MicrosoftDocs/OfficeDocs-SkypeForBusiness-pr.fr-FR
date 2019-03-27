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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 3992c2b4be9cbaaee5f7e7c9648f90d8034bc6aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884891"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Activation ou désactivation des messages hors connexion pour les administrateurs

Vous pouvez envoyer Skype pour messages instantanés Business à vos contacts, même s’ils ne sont pas connectés. Cette fonctionnalité permet à vos contacts de savoir que vous tentiez d’atteindre les. Il est inutile d’attendre que quelqu'un est en ligne avant de les envoyer un message.

Pour les messages hors connexion, il est important de savoir que :

- les messages hors connexion ne seront archivés dans la boîte aux lettres de l'utilisateur ;

- Les messages en mode hors connexion sont envoyés à une boîte aux lettres de l’utilisateur et l’utilisateur sera averti lorsqu’ils se connectent à Skype pour les entreprises.

- Si l’état du destinataire du message est défini sur **Ne pas déranger** ou de **présentation**, ils recevront manqués un message envoyé à partir Skype du destinataire pour client d’entreprise.

Pour plus d’informations, voir [utiliser la messagerie en mode hors connexion dans Skype pour les entreprises](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Pour commencer

## #

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**

1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.

2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.

3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.

4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.

Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).

## #

 **Démarrez une session Windows PowerShell**

1. From the **Start Menu** > **Windows PowerShell**.

2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :

    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

## <a name="turning-on-or-off-offline-im"></a>Activation ou désactivation de la messagerie instantanée hors connexion

> [!NOTE]
> Les Messages en mode hors connexion sont **uniquement** disponibles dans la dernière version de la Skype Click-to-Run pour client d’entreprise et ne sont pas disponibles lorsqu’une ancienne Skype Click-to-Run for Business est utilisée ou un fichier *.msi a été utilisé pour installer le Skype pour client d’entreprise.

Pour activer ou désactiver les Messages en mode hors connexion envoyer des Messages d’en mode hors connexion pour les utilisateurs de votre organisation, définissez _EnableIMAutoArchiving_ sur `True` ou `False`. Par défaut, il est défini sur `True`.

Pour éteindre, utilisez la cmdlet **Set-CsClientPolicy** et exécutez :

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Pour activer ou désactiver l’envoi des Messages en mode hors connexion en mode hors connexion des Messages pour un utilisateur, la valeur _EnableIMAutoArchiving_ `True` ou `False`. Par défaut, cette option est définie sur  `True`. Vous pouvez utiliser une stratégie existante ou créez-en un à l’exemple ci-dessous.


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)



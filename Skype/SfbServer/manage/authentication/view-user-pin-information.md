---
title: Affichage des informations de code confidentiel de l’utilisateur dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Résumé : Permet d’afficher les informations de code PIN utilisateur dans Skype pour Business Server 2015.'
ms.openlocfilehash: 2521c9edba0b16eda6ea799b6b968a8c57bba245
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-user-pin-information-in-skype-for-business-server-2015"></a>Affichage des informations de code confidentiel de l’utilisateur dans Skype Entreprise Server 2015
 
**Résumé :** Utilisateur d’afficher les informations de code PIN dans Skype pour Business Server 2015.
  
Pour participer à une conférence à distance comme un utilisateur authentifié, un Skype pour utilisateur Business Server 2015 avec informations d’identification des Services de domaine Active Directory (AD DS) requiert un numéro d’identification personnel (PIN). Vous pouvez afficher les informations de code PIN d’un utilisateur à partir de Skype pour le panneau de configuration de Business Server.
  
> [!NOTE]
> Vous pouvez afficher les informations de statut du code confidentiel, qui indiquent, par exemple, si le code confidentiel a été défini ou lorsqu’il a été modifié pour la dernière fois, mais vous ne pouvez pas voir le code confidentiel actif en consultant le statut de ce dernier. Si un utilisateur a perdu son code PIN, vous pouvez le réinitialiser en suivant les procédures décrites dans [la valeur à distance conférence d’un utilisateur PIN dans Skype pour Business Server 2015](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Pour afficher des PIN d’un utilisateur de panneau de configuration de Business Server dans Skype

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
   - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
   - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).
    
5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
   a. Cliquez sur **Ajouter un filtre**.
    
   b. Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
   c. Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).
    
   d. Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.
    
    > [!TIP]
    > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**. 
  
   e. Cliquez sur **Rechercher**.
    
    > [!NOTE]
    > Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**. 
  
6. Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Afficher le statut du code confidentiel**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de code PIN utilisateur par les applets de commande de Windows PowerShell à l’aide de

Vous pouvez afficher les informations relatives au code confidentiel de l’utilisateur à l’aide de l’applet de commande Get-CsClientPinInfo. Cette applet de commande peut être exécuté à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-view-user-pin-information"></a>Pour afficher les informations relatives au code confidentiel de l’utilisateur

Pour afficher les informations de code PIN pour un utilisateur, tapez une commande semblable à la suivante dans le Skype pour Business Server Management Shell et appuyez sur ENTRÉE :
    
  ```
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Vous obtiendrez des indications semblables à ceci :

  ```
  Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .
  
## <a name="see-also"></a>Voir aussi

#### 

[La valeur à distance conférence d’un utilisateur PIN dans Skype pour Business Server 2015](set-a-user-s-dial-in-conferencing-pin.md)
  
[Verrouiller ou déverrouiller un utilisateur code PIN dans Skype pour Business Server 2015](lock-or-unlock-a-user-pin.md)


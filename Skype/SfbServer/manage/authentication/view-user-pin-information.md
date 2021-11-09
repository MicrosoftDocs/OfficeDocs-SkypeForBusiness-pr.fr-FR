---
title: Afficher les informations de code confidentiel de l’utilisateur dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Résumé : Affichez les informations de code confidentiel de l’utilisateur Skype Entreprise Server.'
ms.openlocfilehash: 7be0bb49cf1c11d2c9aa18a73aa37dd124d7fb00
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846457"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Afficher les informations de code confidentiel de l’utilisateur dans Skype Entreprise Server
 
**Résumé :** Afficher les informations de code confidentiel de l’utilisateur Skype Entreprise Server.
  
Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur Skype Entreprise Server avec des informations d’identification des services de domaine Active Directory (AD DS) requiert un code confidentiel. Vous pouvez afficher les informations de code confidentiel d’un utilisateur à partir Skype Entreprise Server Panneau de contrôle.
  
> [!NOTE]
> Vous pouvez afficher les informations de statut du code confidentiel, qui indiquent par exemple si le code confidentiel a été défini ou quand il a été modifié pour la dernière fois, mais vous ne pouvez pas voir le code confidentiel actif en consultant le statut de ce dernier. Si un utilisateur a perdu son code confidentiel, vous pouvez le réinitialiser en suivant les procédures dans Définir le code confidentiel de conférence [d’un](set-a-user-s-dial-in-conferencing-pin.md) utilisateur dans Skype Entreprise Server
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Pour afficher le code confidentiel d’un utilisateur dans Skype Entreprise Server de contrôle

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
   - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
   - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).
    
5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
   a. Cliquez sur **Ajouter un filtre**.
    
   b. Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
   c. Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
   d. Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
    
    > [!TIP]
    > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**. 
  
   e. Cliquez sur **Rechercher**.
    
    > [!NOTE]
    > Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**. 
  
6. Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Afficher le statut du code confidentiel**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de code confidentiel de l’utilisateur à l’Windows PowerShell cmdlets

Vous pouvez afficher les informations relatives au code confidentiel de l’utilisateur à l’aide de l’applet de commande Get-CsClientPinInfo. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-view-user-pin-information"></a>Pour afficher les informations relatives au code confidentiel de l’utilisateur

Pour afficher les informations de code confidentiel d’un utilisateur, tapez une commande semblable à la suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Cette action a pour effet de renvoyer des informations similaires à ce qui suit :

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Get-CsConferenceDisclaimer.](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)
  
## <a name="see-also"></a>Voir aussi

[Définir le code confidentiel de conférence d’un utilisateur dans Skype Entreprise Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Verrouiller ou déverrouiller le code confidentiel d’un utilisateur dans Skype Entreprise Server](lock-or-unlock-a-user-pin.md)
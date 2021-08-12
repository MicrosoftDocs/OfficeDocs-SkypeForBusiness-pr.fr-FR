---
title: Verrouiller ou déverrouiller le code confidentiel d’un utilisateur Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Résumé : Verrouillez ou déverrouillez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.'
ms.openlocfilehash: d0871622a045555dcd2da49a6bbbd6721a8d3302a6bf3c7800092e4f7e062d32
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284804"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Verrouiller ou déverrouiller le code confidentiel d’un utilisateur Skype Entreprise Server
 
**Résumé :** Verrouiller ou déverrouiller le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.
  
Vous pouvez verrouiller ou déverrouiller le code confidentiel d’un utilisateur à partir de la section **Utilisateurs** du Panneau de Skype Entreprise Server de contrôle.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Pour verrouiller le code confidentiel d’un utilisateur dans Skype Entreprise Server Panneau de contrôle

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
    
   f. Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Verrouiller le code confidentiel**.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Pour déverrouiller le code confidentiel d’un utilisateur dans Skype Entreprise Server panneau de contrôle

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
    
   f. Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Verrouillage et déverrouillage des pinns utilisateur à l’aide Windows PowerShell cmdlets

Vous pouvez verrouiller et déverrouiller les pins utilisateur à l’aide de Windows PowerShell et des cmdlets Lock-CsClientPin et Unlock-CsClientPin utilisateurs. Vous pouvez exécuter ces cmdlets à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, voir l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-lock-a-user-pin"></a>Pour verrouiller le code confidentiel d’un utilisateur

- Pour verrouiller le code confidentiel d’un utilisateur, utilisez Lock-CsClientPin cmdlet. Par exemple :
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>Pour déverrouiller le code confidentiel d’un utilisateur

- Pour déverrouiller le code confidentiel d’un utilisateur, utilisez Unlock-CsClientPin cmdlet. Par exemple :
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

Pour plus d’informations, voir la rubrique d’aide pour les cmdlets [Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) et [Unlock-CsClientPin.](/powershell/module/skype/unlock-csclientpin?view=skype-ps)
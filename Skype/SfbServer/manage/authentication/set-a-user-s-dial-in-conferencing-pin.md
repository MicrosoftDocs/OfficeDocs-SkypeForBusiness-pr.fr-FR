---
title: Définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Résumé : définissez le code confidentiel de conférence rendez-vous d’un utilisateur pour Skype entreprise Server.'
ms.openlocfilehash: eb025f069156dd54ba772dd866c09adc59d078eb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818736"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Skype entreprise Server
 
**Résumé :** Définissez le code confidentiel de conférence rendez-vous d’un utilisateur pour Skype entreprise Server.
  
Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur de Skype entreprise Server avec des informations d’identification de services de domaine Active Directory (AD DS) nécessite un code confidentiel (PIN). Si un utilisateur oublie le code confidentiel de conférence rendez-vous ou n’a pas défini le code confidentiel à l’aide de Skype entreprise Server, vous pouvez définir le code confidentiel de l’utilisateur dans le panneau de configuration Skype entreprise Server. Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.
  
> [!NOTE]
> Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies sous forme de stratégie. Outre la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur spécifique. 
  
### <a name="to-set-a-users-pin"></a>Pour définir le code confidentiel d’un utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
   - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
   - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).
    
5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
   a. Cliquez sur **Ajouter un filtre**.
    
   b. Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.
    
   c. Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).
    
   d. Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.
    
    > [!TIP]
    > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**. 
  
   e. Cliquez sur **Rechercher**.
    
    > [!NOTE]
    > Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, sélectionnez l’utilisateur, cliquez sur **Action**, puis sur **Déverrouiller le code confidentiel**. 
  
6. Sélectionnez un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Définir le code confidentiel**.
    
7. Dans la boîte de dialogue **Définir le code confidentiel**, effectuez l’une des opérations suivantes :
    
   - Pour permettre à Skype entreprise Server de générer le code confidentiel de l’utilisateur, sélectionnez **générer automatiquement un code confidentiel valide** (par défaut).
    
   - Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.
    
8. Cliquez sur **OK**.
    
9. Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes : 
    
   - Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.
    
   - Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est copié automatiquement dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.
    
10. Cliquez sur **Fermer**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Attribution d’un code confidentiel utilisateur à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez également affecter plusieurs codes confidentiels à l’aide de l’applet de commande Set-CsClientPin. Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Affectation automatique d’un code confidentiel à un utilisateur

La commande ci-dessous affecte un code confidentiel à l’utilisateur Ken Myer. Dans la mesure où le paramètre code confidentiel n’est pas inclus, Skype entreprise Server génère et affecte automatiquement le numéro de broche.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Affectation d’un code confidentiel à un utilisateur

Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .
  


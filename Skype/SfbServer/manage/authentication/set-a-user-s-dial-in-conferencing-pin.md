---
title: Définir des conférences rendez-vous d’un utilisateur code confidentiel dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Résumé : Définir dans les conférences rendez-vous l’utilisateur code confidentiel pour Skype pour Business Server.'
ms.openlocfilehash: 4dc60d10d063e367a7fd696d7625c6a5ad5540b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919359"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Définir des conférences rendez-vous d’un utilisateur code confidentiel dans Skype pour Business Server
 
**Résumé :** Définir dans les conférences rendez-vous l’utilisateur code confidentiel pour Skype pour Business Server.
  
Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un Skype pour utilisateur Business Server avec les informations d’identification des Services de domaine Active Directory (AD DS) requiert un code confidentiel (PIN). Si un utilisateur oublie de conférence rendez-vous code confidentiel ou le code confidentiel n’a pas définie à l’aide de Skype pour Business Server, vous pouvez définir le code confidentiel de l’utilisateur à partir de Skype pour le panneau de configuration serveur Business. Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.
  
> [!NOTE]
> Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies sous forme de stratégie. Outre la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur spécifique. 
  
### <a name="to-set-a-users-pin"></a>Pour définir le code confidentiel d’un utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
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
    
   - Pour autoriser Skype pour Business Server afin de générer le code confidentiel de l’utilisateur, sélectionnez **Générer automatiquement un code confidentiel valide** (par défaut).
    
   - Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.
    
8. Cliquez sur **OK**.
    
9. Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes : 
    
   - Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.
    
   - Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est copié automatiquement dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.
    
10. Cliquez sur **Fermer**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Affectation d’un code confidentiel de l’utilisateur à l’aide des applets de commande Windows PowerShell

Vous pouvez également affecter plusieurs codes confidentiels à l’aide de l’applet de commande Set-CsClientPin. Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Affectation automatique d’un code confidentiel à un utilisateur

La commande ci-dessous affecte un code confidentiel à l’utilisateur Ken Myer. Étant donné que le paramètre Pin n’est pas inclus, Skype pour Business Server va générer automatiquement et l’assigner le code confidentiel.
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Affectation d’un code confidentiel à un utilisateur

Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .
  


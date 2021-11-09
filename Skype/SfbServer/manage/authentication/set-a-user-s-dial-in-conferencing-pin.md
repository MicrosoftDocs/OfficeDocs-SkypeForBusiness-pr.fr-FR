---
title: Définir le code confidentiel de conférence d’un utilisateur dans Skype Entreprise Server
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Résumé : Définissez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.'
ms.openlocfilehash: 45ee99a0e9ab1b10c429fae470e528ffdd2c3326
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856681"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Définir le code confidentiel de conférence d’un utilisateur dans Skype Entreprise Server
 
**Résumé :** Définissez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.
  
Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur Skype Entreprise Server avec des informations d’identification des services de domaine Active Directory (AD DS) requiert un code confidentiel. Si un utilisateur oublie le code confidentiel de conférence ou n’a pas encore le définir à l’aide de Skype Entreprise Server, vous pouvez définir le code confidentiel de l’utilisateur à partir du Panneau de Skype Entreprise Server. Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.
  
> [!NOTE]
> Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies en tant que stratégie. En plus de la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur particulier. 
  
### <a name="to-set-a-users-pin"></a>Pour définir le code confidentiel d’un utilisateur

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
  
6. Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Définir le code confidentiel**.
    
7. Dans la boîte de dialogue **Définir le code confidentiel**, effectuez l’une des opérations suivantes :
    
   - Pour autoriser Skype Entreprise Server générer le code confidentiel de l’utilisateur, sélectionnez Générer automatiquement un code **confidentiel valide** (valeur par défaut).
    
   - Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.
    
8. Cliquez sur **OK**.
    
9. Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes : 
    
   - Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.
    
   - Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est automatiquement copié dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.
    
10. Cliquez sur **Fermer**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Affectation d’un code confidentiel utilisateur à l’aide Windows PowerShell cmdlets

Vous pouvez également affecter des numéros de code confidentiel à l’aide Set-CsClientPin cmdlet. Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Pour attribuer automatiquement un code confidentiel à un utilisateur

La commande suivante affecte un code confidentiel à l’utilisateur Ken Myer. Étant donné que le paramètre Pin n’est pas inclus, Skype Entreprise Server générera et attribuera automatiquement le code confidentiel.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Pour affecter un code confidentiel spécifique à un utilisateur

Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Set-CsClientPin.](/powershell/module/skype/set-csclientpin?view=skype-ps)

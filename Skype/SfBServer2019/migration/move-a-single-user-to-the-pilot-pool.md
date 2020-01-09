---
title: Déplacer un utilisateur unique vers le pool de pilotes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez déplacer un utilisateur de votre liste héritée vers votre pool de pilotes Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration ou de Skype entreprise Server 2019 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool d’inscriptions, pool01.contoso.net est le pool hérité, et les six de ces utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration et de Skype entreprise Server Management Shell.
ms.openlocfilehash: 8964dd3dc868c22cd14389ba70b88d32b6bd145a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988959"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Déplacer un utilisateur unique vers le pool de pilotes

Vous pouvez déplacer un utilisateur de votre liste héritée vers votre pool de pilotes Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration ou de Skype entreprise Server 2019 Management Shell. Dans l’exemple ci-dessous, dans la colonne **pool d’inscriptions** , **pool01.contoso.net** est le pool hérité, et les six de ces utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration et de Skype entreprise Server Management Shell. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Pour déplacer un utilisateur à l’aide du panneau de configuration Skype entreprise Server 2019
  
1. Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.
    
2. Ouvrez **le panneau de configuration Skype entreprise Server**.
    
3. Cliquez sur **utilisateurs**, sur **recherche**, puis sur **Rechercher**.
    
4. Sélectionnez l’utilisateur que vous voulez déplacer vers le pool 2019 de Skype entreprise Server. Dans l’exemple suivant, nous déplacerons l’utilisateur Sara Davis.
    
5. Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.
    
6. Dans la liste déroulante, sélectionnez le pool Skype entreprise Server 2019.
    
7. Cliquez sur **action**, puis sur **déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
  
8. Vérifiez que la colonne **pool d’inscriptions** pour l’utilisateur contient désormais le pool 2019 de Skype entreprise Server, qui indique que l’utilisateur a été déplacée avec succès. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer un utilisateur à l’aide de Skype entreprise Server 2019 Management Shell

1. Ouvrez Skype entreprise Server Management Shell.
    
2. Dans la ligne de commande, tapez ce qui suit : 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Ensuite, dans la ligne de commande, tapez ce qui suit : 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. L’identité **RegistrarPool** pointe désormais vers le pool Skype entreprise Server 2019. La présence de cette identité confirme que l’utilisateur a bien été déplacé. 

    > [!NOTE]
    > Pour plus d’informations sur l’applet de connexion **Get-Csuser** , exécutez : **Get-Help Get-Csuser-detailed**
  


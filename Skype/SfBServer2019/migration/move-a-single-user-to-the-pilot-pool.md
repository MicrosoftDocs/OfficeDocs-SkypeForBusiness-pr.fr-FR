---
title: Déplacer un seul utilisateur vers le pool pilote
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez déplacer un utilisateur de votre pool hérité vers votre pool pilote Skype Entreprise Server 2019 à l’aide du Panneau de commande Skype Entreprise Server 2019 ou de Skype Entreprise Server 2019 Management Shell. Dans l’exemple ci-dessous, dans la colonne Pool de pool01.contoso.net est le pool hérité et ces six utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Skype Entreprise Server 2019 à l’aide du Panneau de contrôle Skype Entreprise Server 2019 et de Skype Entreprise Server Management Shell.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752506"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Déplacer un seul utilisateur vers le pool pilote

Vous pouvez déplacer un utilisateur de votre pool hérité vers votre pool pilote Skype Entreprise Server 2019 à l’aide du Panneau de commande Skype Entreprise Server 2019 ou de Skype Entreprise Server 2019 Management Shell. Dans l’exemple ci-dessous,  dans la colonne Pool de pool01.contoso.net est le pool hérité et ces six utilisateurs sont connectés à ce pool.  Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Skype Entreprise Server 2019 à l’aide du Panneau de contrôle Skype Entreprise Server 2019 et de Skype Entreprise Server Management Shell. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Pour déplacer un utilisateur à l’aide du Panneau de commande Skype Entreprise Server 2019
  
1. Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.
    
2. Ouvrez **le Panneau de contrôle Skype Entreprise Server.**
    
3. Cliquez **sur Utilisateurs,** **sur** Rechercher, puis sur **Rechercher.**
    
4. Sélectionnez un utilisateur à déplacer vers le pool Skype Entreprise Server 2019. Dans cet exemple, nous allons déplacer l’utilisateur Sara Davis.
    
5. Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.
    
6. Dans la liste de listes, sélectionnez le pool Skype Entreprise Server 2019.
    
7. Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
  
8. Vérifiez que la colonne **pool de** serveurs d’inscriptions de l’utilisateur contient désormais le pool Skype Entreprise Server 2019, ce qui indique que l’utilisateur a été déplacé avec succès. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer un utilisateur à l’aide de Skype Entreprise Server 2019 Management Shell

1. Ouvrez Skype Entreprise Server Management Shell.
    
2. Sur la ligne de commande, tapez ce qui suit : 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Ensuite, sur la ligne de commande, tapez ce qui suit : 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **L’identité RegistrarPool** pointe désormais vers le pool Skype Entreprise Server 2019. Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès. 

    > [!NOTE]
    > Pour plus d’informations sur l’cmdlet **Get-CsUser,** exécutez : **Get-Help Get-CsUser -Detailed**
  


---
title: Déplacer plusieurs utilisateurs vers le pool de pilotes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez déplacer plusieurs utilisateurs de votre liste héritée vers votre pool de pilotes Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration ou de Skype entreprise Server 2019 Management Shell.
ms.openlocfilehash: 6c6f61287cfc75b7500317d62de4ea846af1abd3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244571"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Déplacer plusieurs utilisateurs vers le pool de pilotes

Vous pouvez déplacer plusieurs utilisateurs de votre liste héritée vers votre pool de pilotes Skype entreprise Server 2019 à l’aide de Skype entreprise Server 2019 le panneau de configuration ou de Skype entreprise Server 2019 Management Shell.

 **Dans cet article**
  
[Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration Skype entreprise Server 2019](#sectionSection0)
  
[Pour déplacer plusieurs utilisateurs à l’aide de Skype entreprise Server 2019 Management Shell](#sectionSection1)
  
[Pour déplacer tous les utilisateurs en même temps à l’aide de Skype entreprise Server 2019 Management Shell](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration Skype entreprise Server 2019
<a name="sectionSection0"> </a>

1. Ouvrez le panneau de configuration Skype entreprise Server.
    
2. Cliquez sur **utilisateurs**, sur **recherche**, puis sur **Rechercher**.
    
3. Sélectionnez deux utilisateurs que vous voulez déplacer vers le pool Skype entreprise Server 2019. Dans cet exemple, nous allons déménager les utilisateurs Chen Yang et Claus Hansen.
    
     ![Déplacer des utilisateurs vers un pool de Registre spécifique](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Dans le menu **action** , sélectionnez **déplacer les utilisateurs sélectionnés vers le pool**.
    
5. Dans la liste déroulante, sélectionnez le pool Skype entreprise Server 2019.
    
6. Cliquez sur **action**, puis sur **déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
     ![Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Vérifiez que la colonne **pool d’inscriptions** pour les utilisateurs contient désormais le pool Skype entreprise Server 2019, qui indique que les utilisateurs ont été déplacés correctement. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer plusieurs utilisateurs à l’aide de Skype entreprise Server 2019 Management Shell
<a name="sectionSection1"> </a>

1. Ouvrez Skype entreprise Server 2019 Management Shell. 
    
2. Dans la ligne de commande, tapez les informations suivantes et remplacez **User1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous voulez déplacer, puis remplacez **pool_FQDN** par le nom du pool de destination. Dans cet exemple, nous allons déplacer les utilisateurs de Hao Chen et Katie Jordanie. 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemple d’applet de passe PowerShell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Dans la ligne de commande, tapez ce qui suit : 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. L’identité du **pool d’inscriptions** doit maintenant pointer sur le pool que vous avez spécifié comme **pool_FQDN** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a bien été déplacé. Répétez l’étape pour vérifier que l' **utilisateur2** a été déplacé. 
    
     ![Sortie de l’applet de passe PowerShell Get-UsUser-Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer tous les utilisateurs en même temps à l’aide de Skype entreprise Server 2019 Management Shell
<a name="sectionSection2"> </a>

Dans cet exemple, tous les utilisateurs ont été renvoyés vers le pool hérité (pool01.contoso.net). À l’aide de Skype entreprise Server 2019 Management Shell, tous les utilisateurs peuvent être déplacés en même temps que le pool 2019 du serveur Skype entreprise Server (pool02.contoso.net).
  
1. Ouvrez Skype entreprise Server 2019 Management Shell.
    
2. Dans la ligne de commande, tapez ce qui suit : 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Applet de requête PowerShell et résultats dans Management Shell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Exécutez **Get-Csuser** pour l’un des utilisateurs pilote. 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. L’identité du **pool d’inscriptions** pour chaque utilisateur pointe désormais sur le pool que vous avez spécifié comme **pool_FQDN** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a bien été déplacé. 
    
5. Par ailleurs, nous pouvons voir la liste des utilisateurs dans le panneau de configuration Skype entreprise Server 2019 et vérifier que la valeur du pool d’inscriptions pointe désormais vers le pool 2019 de Skype entreprise Server.
    
     ![Liste d’utilisateurs du panneau de configuration Skype entreprise Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  


---
title: Déplacer plusieurs utilisateurs vers le pool pilote
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
description: Vous pouvez déplacer plusieurs utilisateurs de votre pool hérité vers votre pool de test Skype entreprise Server 2019 à l’aide du panneau de configuration de Skype entreprise Server 2019 ou de Skype entreprise Server 2019 Management Shell.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753426"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Déplacer plusieurs utilisateurs vers le pool pilote

Vous pouvez déplacer plusieurs utilisateurs de votre pool hérité vers votre pool de test Skype entreprise Server 2019 à l’aide du panneau de configuration de Skype entreprise Server 2019 ou de Skype entreprise Server 2019 Management Shell.

 **Contenu de cet article :**
  
[Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration de Skype entreprise Server 2019](#sectionSection0)
  
[Pour déplacer plusieurs utilisateurs à l’aide de Skype entreprise Server 2019 Management Shell](#sectionSection1)
  
[Pour déplacer tous les utilisateurs en même temps à l’aide de Skype entreprise Server 2019 Management Shell](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration de Skype entreprise Server 2019
<a name="sectionSection0"> </a>

1. Ouvrez le panneau de configuration de Skype entreprise Server.
    
2. Cliquez sur **utilisateurs**, sur **recherche**, puis sur **Rechercher**.
    
3. Sélectionnez deux utilisateurs que vous souhaitez déplacer vers le pool Skype entreprise Server 2019. Dans cet exemple, nous allons déplacer les utilisateurs Chen Yang et Claus Hansen.
    
     ![Déplacer des utilisateurs vers un pool de registres spécifique](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.
    
5. Dans la liste déroulante, sélectionnez le pool Skype entreprise Server 2019.
    
6. Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
     ![Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Vérifiez que la colonne pool de serveurs d' **inscriptions** des utilisateurs contient désormais le pool Skype entreprise Server 2019, ce qui indique que les utilisateurs ont été déplacés avec succès. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer plusieurs utilisateurs à l’aide de Skype entreprise Server 2019 Management Shell
<a name="sectionSection1"> </a>

1. Ouvrez Skype entreprise Server 2019 Management Shell. 
    
2. Sur la ligne de commande, tapez ce qui suit et remplacez **utilisateur1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous souhaitez déplacer, et remplacez **pool_FQDN** par le nom du pool de destination. Dans cet exemple, nous allons déplacer les utilisateurs Hao Chen et Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemple de cmdlet PowerShell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Dans la ligne de commande, tapez le code suivant : 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. L’identité **Registrar Pool** doit désormais pointer vers le pool que vous avez spécifié en tant que **pool_FQDN** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès. Répétez l’étape pour **vérifier que l'** utilisateur 2 a été déplacé. 
    
     ![Sortie de l’applet de commande PowerShell Get-UsUser-Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer tous les utilisateurs en même temps à l’aide de Skype entreprise Server 2019 Management Shell
<a name="sectionSection2"> </a>

Dans cet exemple, tous les utilisateurs ont été renvoyés au pool hérité (pool01.contoso.net). À l’aide de Skype entreprise Server 2019 Management Shell, nous allons déplacer tous les utilisateurs en même temps vers le pool de Skype entreprise Server 2019 (pool02.contoso.net).
  
1. Ouvrez Skype entreprise Server 2019 Management Shell.
    
2. Dans la ligne de commande, tapez le code suivant : 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet PowerShell et résultats dans Management Shell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Exécutez **Get-Csuser** pour l’un des utilisateurs pilotes. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. L’identité du pool de serveurs d' **inscriptions** pour chaque utilisateur pointe désormais vers le pool que vous avez spécifié comme **pool_FQDN** à l’étape précédente. Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès. 
    
5. En outre, nous pouvons afficher la liste des utilisateurs dans le panneau de configuration de Skype entreprise Server 2019 et vérifier que la valeur de pool de serveurs d’inscriptions pointe désormais vers le pool de serveurs 2019 de Skype entreprise Server.
    
     ![Liste des utilisateurs du panneau de configuration de Skype entreprise Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  


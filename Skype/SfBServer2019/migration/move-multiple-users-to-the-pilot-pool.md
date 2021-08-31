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
ms.localizationpriority: medium
description: Vous pouvez déplacer plusieurs utilisateurs de votre pool hérité vers votre pool pilote Skype Entreprise Server 2019 à l’aide du Panneau de Skype Entreprise Server 2019 ou de Skype Entreprise Server 2019 Management Shell.
ms.openlocfilehash: fc4d14d26a76ff4dbfc690fc7517aba77afd253f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726313"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Déplacer plusieurs utilisateurs vers le pool pilote

Vous pouvez déplacer plusieurs utilisateurs de votre pool hérité vers votre pool pilote Skype Entreprise Server 2019 à l’aide du Panneau de Skype Entreprise Server 2019 ou de Skype Entreprise Server 2019 Management Shell.

 **Contenu de cet article :**
  
[Pour déplacer plusieurs utilisateurs à l’aide du Panneau Skype Entreprise Server 2019](#sectionSection0)
  
[Pour déplacer plusieurs utilisateurs à l’aide Skype Entreprise Server 2019 Management Shell](#sectionSection1)
  
[Pour déplacer tous les utilisateurs en même temps à l’aide Skype Entreprise Server 2019 Management Shell](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Pour déplacer plusieurs utilisateurs à l’aide du Panneau Skype Entreprise Server 2019
<a name="sectionSection0"> </a>

1. Ouvrez Skype Entreprise Server panneau de contrôle.
    
2. Cliquez **sur Utilisateurs,** **sur** Rechercher, puis sur **Rechercher.**
    
3. Sélectionnez deux utilisateurs à déplacer vers le pool Skype Entreprise Server 2019. Dans cet exemple, nous allons déplacer les utilisateurs Chen Yang et Claus Hansen.
    
     ![Déplacez les utilisateurs vers un pool d’inscription spécifique.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.
    
5. Dans la liste de listes, sélectionnez le pool Skype Entreprise Server 2019.
    
6. Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
     ![Boîte de dialogue Déplacer les utilisateurs, pool de bureaux d’inscriptions de destination.](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Vérifiez que la colonne **du pool** de bureaux d’inscriptions pour les utilisateurs contient désormais le pool Skype Entreprise Server 2019, ce qui indique que les utilisateurs ont été déplacés avec succès. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer plusieurs utilisateurs à l’aide Skype Entreprise Server 2019 Management Shell
<a name="sectionSection1"> </a>

1. Ouvrez Skype Entreprise Server 2019 Management Shell. 
    
2. Sur la ligne de commande, tapez ce qui suit et remplacez **User1** et **User2** par des noms d’utilisateurs spécifiques que vous souhaitez déplacer, et remplacez **pool_FQDN** par le nom du pool de destination. Dans cet exemple, nous allons déplacer les utilisateurs Hao Chen et Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemple d'Get-CsUser PowerShell.](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Dans la ligne de commande, tapez le code suivant : 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. L’identité **Registrar Pool** doit désormais pointer vers le pool que vous avez spécifié en tant que **pool_FQDN** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès. Répétez l’étape pour **vérifier que User2** a été déplacé. 
    
     ![Sortie de l'Get-UsUser -Identity de PowerShell.](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer tous les utilisateurs en même temps à l’aide Skype Entreprise Server 2019 Management Shell
<a name="sectionSection2"> </a>

Dans cet exemple, tous les utilisateurs ont été renvoyés au pool hérité (pool01.contoso.net). À l’aide Skype Entreprise Server 2019 Management Shell, nous allons déplacer tous les utilisateurs en même temps vers le pool Skype Entreprise Server 2019 (pool02.contoso.net).
  
1. Ouvrez Skype Entreprise Server 2019 Management Shell.
    
2. Dans la ligne de commande, tapez le code suivant : 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet PowerShell et résultats dans Management Shell.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Exécutez **Get-CsUser** pour l’un des utilisateurs pilotes. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. **L’identité du pool** de bureaux d’inscriptions pour chaque utilisateur pointe maintenant vers le pool que vous avez spécifié comme **pool_FQDN** l’étape précédente. Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès. 
    
5. En outre, nous pouvons afficher la liste des utilisateurs dans le Panneau de Skype Entreprise Server 2019 et vérifier que la valeur du pool de bureaux d’inscriptions pointe désormais vers le pool Skype Entreprise Server 2019.
    
     ![Skype Entreprise Server d’utilisateurs du Panneau de contrôle 2019.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  


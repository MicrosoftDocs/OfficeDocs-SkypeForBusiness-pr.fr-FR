---
title: Déplacer plusieurs utilisateurs vers le pool pilote
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez déplacer plusieurs utilisateurs à partir de votre pool hérité vers votre Skype pour le pool pilote Business Server 2019 à l’aide de Skype pour Business Server 2019 le panneau de configuration ou Skype pour Business Server 2019 Management Shell.
ms.openlocfilehash: 3b01613e16e41ed2ee7aac7bc6c443e19db933c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372508"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Déplacer plusieurs utilisateurs vers le pool pilote

Vous pouvez déplacer plusieurs utilisateurs à partir de votre pool hérité vers votre Skype pour le pool pilote Business Server 2019 à l’aide de Skype pour Business Server 2019 le panneau de configuration ou Skype pour Business Server 2019 Management Shell.

 **Dans cet article**
  
[Pour déplacer plusieurs utilisateurs à l’aide de la Skype pour Business Server 2019 le panneau de configuration](#sectionSection0)
  
[Pour déplacer plusieurs utilisateurs à l’aide de la Skype pour Business Server 2019 Management Shell](#sectionSection1)
  
[Pour déplacer tous les utilisateurs en même temps à l’aide de la Skype pour Business Server 2019 Management Shell](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Pour déplacer plusieurs utilisateurs à l’aide de la Skype pour Business Server 2019 le panneau de configuration
<a name="sectionSection0"> </a>

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Cliquez sur **utilisateurs**, cliquez sur **Rechercher**, puis cliquez sur **Rechercher**.
    
3. Sélectionnez les deux utilisateurs que vous souhaitez déplacer vers le Skype pour Business Server 2019 pool. Dans cet exemple, nous déplace les utilisateurs Chen Yang et Claus Hansen.
    
     ![Déplacer les utilisateurs vers le pool de Registre spécifique](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Dans le menu **Action** , sélectionnez **déplacer les utilisateurs sélectionnés vers le pool**.
    
5. Dans la liste déroulante, sélectionnez le Skype pour Business Server 2019 pool.
    
6. Cliquez sur **Action**, puis cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
     ![Déplacer des utilisateurs, boîte de dialogue destination du serveur d’inscriptions pool](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Vérifiez que la colonne **pool de serveurs d’inscriptions** pour les utilisateurs contient maintenant le Skype pour Business Server 2019 pool, ce qui indique que les utilisateurs ont été déplacés avec succès. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer plusieurs utilisateurs à l’aide de la Skype pour Business Server 2019 Management Shell
<a name="sectionSection1"> </a>

1. Ouvrez le Skype pour Business Server 2019 Management Shell. 
    
2. Sur la ligne de commande, tapez la commande suivante et remplacez **User1** et **User2** par les noms d’utilisateur spécifiques à déplacer et **pool_fqdn par le nom du pool de destination** . Dans cet exemple nous déplace les utilisateurs Hao Chen et Katie Jordan. 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemple d’applet de commande PowerShell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Dans la ligne de commande, tapez ce qui suit : 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. L’identité du **Pool de serveurs d’inscriptions** doit désormais pointer vers le pool que vous avez spécifié comme **pool_FQDN** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès. Répétez l’étape pour vérifier que **l’utilisateur 2** a été déplacé. 
    
     ![Sortie de PowerShell Get-UsUser-Identity applet de commande](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer tous les utilisateurs en même temps à l’aide de la Skype pour Business Server 2019 Management Shell
<a name="sectionSection2"> </a>

Dans cet exemple, tous les utilisateurs ont été renvoyés vers le pool hérité (pool01.contoso.net). À l’aide de la Skype pour Business Server 2019 Management Shell, nous déplace tous les utilisateurs en même temps vers la Skype pour le pool d’entreprise Server 2019 (pool02.contoso.net).
  
1. Ouvrez le Skype pour Business Server 2019 Management Shell.
    
2. Dans la ligne de commande, tapez ce qui suit : 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Applet de commande PowerShell et les résultats dans Management Shell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Exécutez **Get-CsUser** pour un des utilisateurs pilotes. 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. L’identité du **Pool de serveurs d’inscriptions** pour chaque utilisateur pointe désormais vers le pool que vous avez spécifié comme **pool_FQDN** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès. 
    
5. En outre, nous pouvons afficher la liste des utilisateurs dans le Skype pour Business Server 2019 le panneau de configuration et vérifiez que la valeur Registrar Pool pointe désormais vers le Skype pour Business Server 2019 pool.
    
     ![Skype pour la liste des utilisateurs Business Server 2019 le panneau de configuration](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  


---
title: Déplacement d’un utilisateur vers le pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez déplacer un utilisateur à partir de votre pool hérité vers votre Skype pour le pool pilote Business Server 2019 à l’aide de Skype pour Business Server 2019 le panneau de configuration ou Skype pour Business Server 2019 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool de serveurs d’inscriptions, pool01.contoso.net est le pool hérité et tous les six de ces utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur à votre Skype pour Business Server 2019 pool à l’aide de Skype pour Business Server 2019 le panneau de configuration et Skype pour Business Server Management Shell.
ms.openlocfilehash: 94896ce2ea05a3102d5a7643e3f26430e74bfe19
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880248"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Déplacement d’un utilisateur vers le pool pilote

Vous pouvez déplacer un utilisateur à partir de votre pool hérité vers votre Skype pour le pool pilote Business Server 2019 à l’aide de Skype pour Business Server 2019 le panneau de configuration ou Skype pour Business Server 2019 Management Shell. Dans l’exemple ci-dessous, dans la colonne **pool de serveurs d’inscriptions** , **pool01.contoso.net** est le pool hérité et tous les six de ces utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur à votre Skype pour Business Server 2019 pool à l’aide de Skype pour Business Server 2019 le panneau de configuration et Skype pour Business Server Management Shell. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Pour déplacer un utilisateur à l’aide de la Skype pour Business Server 2019 le panneau de configuration
  
1. Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.
    
2. Ouvrez **Skype pour le panneau de configuration serveur Business**.
    
3. Cliquez sur **utilisateurs**, cliquez sur **Rechercher**, puis cliquez sur **Rechercher**.
    
4. Sélectionnez un utilisateur que vous souhaitez déplacer vers le Skype pour Business Server 2019 pool. Dans l’exemple suivant, nous déplacerons l’utilisateur Sara Davis.
    
5. Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.
    
6. Dans la liste déroulante, sélectionnez le Skype pour Business Server 2019 pool.
    
7. Cliquez sur **Action**, puis cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
  
8. Vérifiez que la colonne **pool de serveurs d’inscriptions** de l’utilisateur contient maintenant le Skype pour Business Server 2019 pool, ce qui indique que l’utilisateur a été déplacé avec succès. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Pour déplacer un utilisateur à l’aide de la Skype pour Business Server 2019 Management Shell

1. Ouvrez le Skype pour Business Server Management Shell.
    
2. Dans la ligne de commande, tapez ce qui suit : 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Ensuite, à l’invite de commandes, tapez ce qui suit : 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. L’identité **RegistrarPool** pointe désormais vers le Skype pour Business Server 2019 pool. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès. 

    > [!NOTE]
    > Pour plus d’informations sur l’applet de commande **Get-CsUser** , exécutez : **Get-Help Get-CsUser-détaillées**
  


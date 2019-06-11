---
title: Déplacer plusieurs utilisateurs vers le pool de pilotes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc3104566841cc70eeee489a4b8812a6b8039a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Déplacer plusieurs utilisateurs vers le pool de pilotes

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

Vous pouvez déplacer plusieurs utilisateurs de votre pool Lync Server 2010 vers votre pool de pilotes Lync Server 2013 à l’aide de Lync Server 2013 panneau de configuration ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration de Lync Server 2013

1.  Ouvrez le **Paneau de configuration Lync Server**.

2.  Cliquez successivement sur **Utilisateurs**, Rechercher, puis sur **Trouver**.

3.  Sélectionnez deux utilisateurs que vous voulez déplacer vers le pool Lync Server 2013. Dans cet exemple, nous allons déménager les utilisateurs Chen Yang et Claus Hansen.
    
    ![Déplacer des utilisateurs vers un pool de Registre spécifique] (images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Déplacer des utilisateurs vers un pool de Registre spécifique")  

4.  Dans le menu **action** , sélectionnez **déplacer les utilisateurs sélectionnés vers le pool**.

5.  Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

6.  Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur OK.
    
    ![Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination")  

7.  Vérifiez que la colonne **pool d’inscriptions** pour les utilisateurs contient désormais le pool Lync Server 2013, qui indique que les utilisateurs ont été déplacés correctement.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer plusieurs utilisateurs à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Dans la ligne de commande, tapez les informations suivantes et remplacez **User1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous voulez déplacer, puis remplacez **FQDN du pool\_** par le nom du pool de destination. Dans cet exemple, nous allons déplacer les utilisateurs de Hao Chen et Katie Jordanie.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Exemple d’applet de passe PowerShell Get-Csuser] (images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Exemple d’applet de passe PowerShell Get-Csuser")  

3.  Dans la ligne de commande, tapez ce qui suit:
    
        Get-CsUser -Identity "User1"

4.  L’identité du **pool d’inscriptions** doit maintenant pointer sur le pool que vous avez spécifié comme **nom de domaine complet du pool\_** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a bien été déplacé. Répétez l’étape pour vérifier que l' **utilisateur2** a été déplacé.
    
    ![Sortie de l’applet de passe PowerShell Get-UsUser-Identity] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Sortie de l’applet de passe PowerShell Get-UsUser-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer tous les utilisateurs en même temps à l’aide de Lync Server 2013 Management Shell

Dans cet exemple, tous les utilisateurs ont été retournés au pool Lync Server 2010 (pool01.contoso.net). À l’aide de Lync Server 2013 Management Shell, tous les utilisateurs sont déplacés en même temps que le pool Lync Server 2013 (pool02.contoso.net).

1.  Ouvrez **Lync Server 2013 Management Shell**.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Applet de requête PowerShell et résultats dans Management Shell] (images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Applet de requête PowerShell et résultats dans Management Shell")  

3.  Exécutez ensuite **Get-Csuser** pour l’un des utilisateurs pilote.
    
        Get-CsUser -Identity "Hao Chen"

4.  L’identité du **pool d’inscriptions** pour chaque utilisateur pointe désormais sur le pool que vous avez\_spécifié comme «nom de domaine complet du pool» à l’étape précédente. La présence de cette identité confirme que l’utilisateur a bien été déplacé.

5.  Par ailleurs, nous pouvons afficher la liste des utilisateurs dans le panneau de configuration de Lync Server 2013 et vérifier que la valeur du pool d’inscriptions pointe désormais vers le pool Lync Server 2013.
    
    ![Liste des utilisateurs de Lync Server 2013 Control Panel] (images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Liste des utilisateurs de Lync Server 2013 Control Panel")  

</div>

</div>

<span> </span>

</div>

</div>

</div>


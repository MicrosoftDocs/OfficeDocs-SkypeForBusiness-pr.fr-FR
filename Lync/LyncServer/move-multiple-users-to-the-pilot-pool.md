---
title: Déplacer plusieurs utilisateurs vers le pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81b5ad16b36063c217d90c4c8f1e8a2e7fa3c0ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Déplacer plusieurs utilisateurs vers le pool pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Vous pouvez déplacer plusieurs utilisateurs de votre pool Lync Server 2010 vers votre pool de pilote Lync Server 2013 à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration Lync Server 2013

1.  Ouvrez le **Panneau de configuration Lync Server**.

2.  Cliquez sur **Utilisateurs**, sur Rechercher, puis sur **Rechercher**.

3.  Sélectionnez deux utilisateurs que vous souhaitez déplacer vers le pool Lync Server 2013. Dans cet exemple, nous allons déplacer les utilisateurs Chen Yang et Claus Hansen.
    
    ![Déplacer des utilisateurs vers un pool de registres spécifique](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Déplacer des utilisateurs vers un pool de registres spécifique")  

4.  Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.

5.  Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

6.  Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur OK.
    
    ![Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination")  

7.  Vérifiez que la colonne pool de serveurs d' **inscriptions** des utilisateurs contient désormais le pool Lync Server 2013, ce qui indique que les utilisateurs ont été déplacés avec succès.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer plusieurs utilisateurs à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Sur la ligne de commande, tapez ce qui suit et remplacez **utilisateur1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous souhaitez déplacer et remplacer le nom de **domaine complet du pool\_** par le nom du pool de destination. Dans cet exemple, nous allons déplacer les utilisateurs Hao Chen et Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Exemple de cmdlet PowerShell Get-CsUser](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Exemple de cmdlet PowerShell Get-CsUser")  

3.  Sur la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -Identity "User1"

4.  L’identité du pool de serveurs d' **inscriptions** doit désormais pointer vers le pool que vous avez spécifié comme **nom de domaine complet du pool\_** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès. Répétez cette étape pour vérifier que **User2** a été déplacé.
    
    ![Sortie de l’applet de commande PowerShell Get-UsUser-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Sortie de l’applet de commande PowerShell Get-UsUser-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer tous les utilisateurs en même temps à l’aide de Lync Server 2013 Management Shell

Dans cet exemple, tous les utilisateurs ont été renvoyés au pool Lync Server 2010 (pool01.contoso.net). À l’aide de Lync Server 2013 Management Shell, nous allons déplacer tous les utilisateurs en même temps vers le pool Lync Server 2013 (pool02.contoso.net).

1.  Ouvrez **Lync Server 2013 Management Shell**.

2.  Dans la ligne de commande, tapez le code suivant :
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Cmdlet PowerShell et résultats dans Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet PowerShell et résultats dans Management Shell")  

3.  Exécutez ensuite **Get-CsUser** pour l’un des utilisateurs pilotes.
    
        Get-CsUser -Identity "Hao Chen"

4.  L’identité du pool de serveurs d' **inscriptions** pour chaque utilisateur pointe désormais vers le pool que\_vous avez spécifié en tant que « nom de domaine complet du pool » à l’étape précédente. Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès.

5.  De plus, nous pouvons afficher la liste des utilisateurs dans le panneau de configuration Lync Server 2013 et vérifier que la valeur de pool de serveurs d’inscriptions pointe désormais vers le pool Lync Server 2013.
    
    ![Liste des utilisateurs de Lync Server 2013 panneau de configuration](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Liste des utilisateurs de Lync Server 2013 panneau de configuration")  

</div>

</div>

<span> </span>

</div>

</div>

</div>


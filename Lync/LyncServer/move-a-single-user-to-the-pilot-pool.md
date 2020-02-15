---
title: Déplacer un seul utilisateur vers le pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cce0a2110c0c40b105bf2b3d26bf4f99b901522
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Déplacer un seul utilisateur vers le pool pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

Vous pouvez déplacer un utilisateur de votre pool Lync Server 2010 vers votre pool Lync Server 2013 pilote à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool de serveurs d’inscriptions, **pool01.contoso.net** est le pool Lync Server 2010 et tous les six de ces utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Lync Server 2013 à l’aide du panneau de configuration Lync Server 2013 et de Lync Server Management Shell.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Pour déplacer un utilisateur à l’aide du panneau de configuration Lync Server 2013

**Liste des utilisateurs dans le panneau de configuration Lync Server 2013**

![Panneau de configuration Lync Server, boîte de dialogue déplacer un utilisateur](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Panneau de configuration Lync Server, boîte de dialogue déplacer un utilisateur")

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le **Panneau de configuration Lync Server**.

3.  Cliquez sur **Utilisateurs**, sur Rechercher, puis sur **Rechercher**.

4.  Sélectionnez un utilisateur que vous souhaitez déplacer vers le pool Lync Server 2013. Dans cet exemple, nous allons déplacer l’utilisateur Sara Davis.

5.  Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.

6.  Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

7.  Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
    ![Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination")  

8.  Vérifiez que la colonne pool de serveurs d' **inscriptions** de l’utilisateur contient désormais le pool Lync Server 2013, ce qui indique que l’utilisateur a été déplacé avec succès.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer un utilisateur à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Sur la ligne de commande, tapez ce qui suit :
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Ensuite, sur la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -Identity "David Pelton"

4.  L’identité **RegistrarPool** pointe désormais vers le pool Lync Server 2013. Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès.
    
    ![Sortie de l’applet de commande Get-CsUser avec le filtre d’identité](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Sortie de l’applet de commande Get-CsUser avec le filtre d’identité")  
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur l’applet de commande <STRONG>Get-CsUser</STRONG>, exécutez : <STRONG>Get-Help Get-CsUser –Detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


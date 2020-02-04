---
title: Déplacer un utilisateur unique vers le pool de pilotes
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
ms.openlocfilehash: c14c4a772ced3939d979bd8d4cd053207b0c5613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Déplacer un utilisateur unique vers le pool de pilotes

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

Vous pouvez déplacer un utilisateur de votre pool Lync Server 2010 vers votre pool de pilotes Lync Server 2013 à l’aide de Lync Server 2013 panneau de configuration ou de Lync Server 2013 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool d’inscriptions, **pool01.contoso.net** est le pool Lync Server 2010 et les six utilisateurs sont connectés à ce pool. Pour déplacer un utilisateur vers votre pool Lync Server 2013 à l’aide de Lync Server 2013 Control Panel et de Lync Server Management Shell, procédez comme suit.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Pour déplacer un utilisateur à l’aide du panneau de configuration de Lync Server 2013

**Liste des utilisateurs dans le panneau de configuration de Lync Server 2013**

![Panneau de configuration de Lync Server, boîte de dialogue déplacer l’utilisateur](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Panneau de configuration de Lync Server, boîte de dialogue déplacer l’utilisateur")

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le **Paneau de configuration Lync Server**.

3.  Cliquez successivement sur **Utilisateurs**, Rechercher, puis sur **Trouver**.

4.  Sélectionnez l’utilisateur que vous voulez déplacer vers le pool Lync Server 2013. Dans l’exemple suivant, nous déplacerons l’utilisateur Sara Davis.

5.  Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.

6.  Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

7.  Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
    ![Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination")  

8.  Vérifiez que la colonne **pool d’inscriptions** pour l’utilisateur contient désormais le pool Lync Server 2013, qui indique que l’utilisateur a été déplacée correctement.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer un utilisateur à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Ensuite, dans la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -Identity "David Pelton"

4.  L’identité **RegistrarPool** pointe désormais vers le pool Lync Server 2013. La présence de cette identité confirme que l’utilisateur a bien été déplacé.
    
    ![Sortie de l’applet de requête get-CsUser avec le filtre d’identité](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Sortie de l’applet de requête get-CsUser avec le filtre d’identité")  
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur l’applet de connexion <STRONG>Get-Csuser</STRONG> , exécutez : <STRONG>Get-Help Get-Csuser-detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


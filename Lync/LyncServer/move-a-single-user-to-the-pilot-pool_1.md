---
title: Déplacer un utilisateur unique vers le pool de pilotes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cb89fde2a62858c3bd9a402207f4b23fd51643
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Déplacer un utilisateur unique vers le pool de pilotes

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Vous pouvez déplacer un utilisateur de votre pool Office Communications Server 2007 R2 vers votre pool de pilotes Lync Server 2013 à l’aide de Lync Server 2013 panneau de configuration ou de Lync Server 2013 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool de bureaux d’enregistrement, ** \<Office Communications Server\> ** est le pool Office Communications Server 2007 R2, et ces six utilisateurs sont connectés à ce pool. Pour déplacer un utilisateur vers votre pool Lync Server 2013 à l’aide de Lync Server 2013 Control Panel et de Lync Server Management Shell, procédez comme suit.

![Rechercher des utilisateurs OCS dans le panneau de configuration de Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Rechercher des utilisateurs OCS dans le panneau de configuration de Lync Server")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Pour déplacer un utilisateur à l’aide du panneau de configuration de Lync Server 2013

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le Paneau de configuration Lync Server.

3.  Cliquez sur **utilisateurs**.

4.  Dans l’onglet **recherche** , cliquez sur le bouton **Rechercher** .

5.  Cliquez ensuite sur **Ajouter un filtre**.

6.  Créer un filtre dans lequel l' **utilisateur d’Office Communications Server** est égal à **vrai**.

7.  Cliquez sur **Rechercher** pour rechercher les anciens utilisateurs d’Office Communications Server 2007 R2.
    
    ![Rechercher des utilisateurs OCS dans le panneau de configuration de Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Rechercher des utilisateurs OCS dans le panneau de configuration de Lync Server")  

8.  Sélectionnez l’utilisateur que vous voulez déplacer vers le pool Lync Server 2013. Dans l’exemple suivant, nous déplacerons l’utilisateur Sara Davis.

9.  Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.

10. Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

11. Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
    ![Configuration du pool de destination dans la boîte de dialogue déplacer des utilisateurs](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Configuration du pool de destination dans la boîte de dialogue déplacer des utilisateurs")  

12. Vérifiez que la colonne du **pool d’inscriptions** pour l’utilisateur contient désormais le pool Lync Server 2013, qui indique que l’utilisateur a été correctement déplacé.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer un utilisateur à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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


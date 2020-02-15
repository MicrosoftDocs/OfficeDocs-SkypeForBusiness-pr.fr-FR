---
title: Déplacer un seul utilisateur vers le pool pilote
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
ms.openlocfilehash: 051e5b0c550b76dc61aa7935ea8867cc282ddd24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Déplacer un seul utilisateur vers le pool pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Vous pouvez déplacer un utilisateur de votre pool Office Communications Server 2007 R2 vers votre pool de pilote Lync Server 2013 à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool de serveurs d’inscriptions, ** \<Office Communications Server\> ** est le pool Office Communications Server 2007 R2, et ces six utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Lync Server 2013 à l’aide du panneau de configuration Lync Server 2013 et de Lync Server Management Shell.

![Rechercher des utilisateurs OCS dans le panneau de configuration Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Rechercher des utilisateurs OCS dans le panneau de configuration Lync Server")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Pour déplacer un utilisateur à l’aide du panneau de configuration Lync Server 2013

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Cliquez sur **Utilisateurs**.

4.  Sous l’onglet **Recherche d’un utilisateur**, cliquez sur le bouton **Rechercher**.

5.  Cliquez ensuite sur **Ajouter un filtre**.

6.  Créez un filtre pour lequel **Utilisateur Office Communications Server** a la valeur **True**.

7.  Cliquez sur **Rechercher** pour rechercher les utilisateurs hérités d’Office Communications Server 2007 R2.
    
    ![Rechercher des utilisateurs OCS dans le panneau de configuration Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Rechercher des utilisateurs OCS dans le panneau de configuration Lync Server")  

8.  Sélectionnez un utilisateur que vous souhaitez déplacer vers le pool Lync Server 2013. Dans cet exemple, nous allons déplacer l’utilisateur Sara Davis.

9.  Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.

10. Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

11. Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
    ![Définition du pool de destination dans la boîte de dialogue déplacer des utilisateurs](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Définition du pool de destination dans la boîte de dialogue déplacer des utilisateurs")  

12. Vérifiez que la colonne pool de serveurs d' **inscriptions** de l’utilisateur contient désormais le pool Lync Server 2013, ce qui indique que l’utilisateur a été déplacé avec succès.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer un utilisateur à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Sur la ligne de commande, tapez ce qui suit :
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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


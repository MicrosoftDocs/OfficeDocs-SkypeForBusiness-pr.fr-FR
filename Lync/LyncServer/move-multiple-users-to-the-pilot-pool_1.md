---
title: Déplacer plusieurs utilisateurs vers le pool de pilotes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70d031481746f9f7408cc7b5e36081bb977b189d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Déplacer plusieurs utilisateurs vers le pool de pilotes

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Vous pouvez déplacer plusieurs utilisateurs à partir de votre pool Office Communications Server 2007 R2 vers votre pool de pilotes Lync Server 2013 à l’aide de Lync Server 2013 panneau de configuration ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration de Lync Server 2013

1.  Ouvrez le **Paneau de configuration Lync Server**.

2.  Dans l’onglet **recherche** , cliquez sur le bouton **Rechercher** .

3.  Cliquez ensuite sur **Ajouter un filtre**.

4.  Créer un filtre dans lequel l' **utilisateur d’Office Communications Server** est égal à **vrai**.

5.  Cliquez sur **Rechercher** pour rechercher les anciens utilisateurs d’Office Communications Server 2007 R2.

6.  Sélectionnez deux utilisateurs que vous voulez déplacer vers le pool Lync Server 2013. Dans cet exemple, nous allons déménager les utilisateurs Chen Yang et Claus Hansen.
    
    ![Liste d’utilisateurs affichée lors de la recherche d’utilisateurs OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Liste d’utilisateurs affichée lors de la recherche d’utilisateurs OCS")  

7.  Dans le menu **action** , sélectionnez **déplacer les utilisateurs sélectionnés vers le pool**.

8.  Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

9.  Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur OK.
    
    ![Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Déplacer des utilisateurs, boîte de dialogue pool d’inscriptions de destination")  

10. Vérifiez que la colonne **pool d’inscriptions** pour les utilisateurs contient désormais le pool Lync Server 2013, qui indique que les utilisateurs ont été déplacés correctement.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer plusieurs utilisateurs à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Dans la ligne de commande, tapez les informations suivantes et remplacez **User1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous voulez déplacer, puis remplacez **FQDN du pool\_** par le nom du pool de destination. Dans cet exemple, nous allons déplacer les utilisateurs de Hao Chen et Katie Jordanie.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Exemple de cmdlet pour déplacer un utilisateur hérité](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Exemple de cmdlet pour déplacer un utilisateur hérité")  

3.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -Identity "User1"

4.  L’identité du **pool d’inscriptions** doit maintenant pointer sur le pool que vous avez spécifié comme **nom de domaine complet du pool\_** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a bien été déplacé. Répétez l’étape pour vérifier que l' **utilisateur2** a été déplacé.
    
    ![Sortie de l’applet de passe PowerShell Get-UsUser-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Sortie de l’applet de passe PowerShell Get-UsUser-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer tous les utilisateurs en même temps à l’aide de Lync Server 2013 Management Shell

Dans cet exemple, tous les utilisateurs ont été retournés au pool Office Communications Server 2007 R2 (pool01.contoso.net). À l’aide de Lync Server 2013 Management Shell, tous les utilisateurs sont déplacés en même temps que le pool Lync Server 2013 (pool02.contoso.net).

1.  Ouvrez **Lync Server 2013 Management Shell**.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Exemple de cmdlet pour déplacer tous les anciens utilisateurs d’un pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Exemple de cmdlet pour déplacer tous les anciens utilisateurs d’un pool")  

3.  Exécutez ensuite **Get-Csuser** pour l’un des utilisateurs pilote.
    
        Get-CsUser -Identity "Hao Chen"

4.  L’identité du **pool d’inscriptions** pour chaque utilisateur pointe désormais sur le pool que vous avez\_spécifié comme « nom de domaine complet du pool » à l’étape précédente. La présence de cette identité confirme que l’utilisateur a bien été déplacé.

5.  Par ailleurs, nous pouvons afficher la liste des utilisateurs dans le panneau de configuration de Lync Server 2013 et vérifier que la valeur du pool d’inscriptions pointe désormais vers le pool Lync Server 2013.
    
    ![Liste des utilisateurs de Lync Server 2013 Control Panel](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Liste des utilisateurs de Lync Server 2013 Control Panel")  

</div>

</div>

<span> </span>

</div>

</div>

</div>


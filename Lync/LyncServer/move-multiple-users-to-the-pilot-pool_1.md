---
title: Déplacer plusieurs utilisateurs vers le pool pilote
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
ms.openlocfilehash: d659e879b821f27c159cee874dae9db0796f079b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Déplacer plusieurs utilisateurs vers le pool pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Vous pouvez déplacer plusieurs utilisateurs de votre pool Office Communications Server 2007 R2 vers votre pool de pilote Lync Server 2013 à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Pour déplacer plusieurs utilisateurs à l’aide du panneau de configuration Lync Server 2013

1.  Ouvrez le **Panneau de configuration Lync Server**.

2.  Sous l’onglet **Recherche d’un utilisateur**, cliquez sur le bouton **Rechercher**.

3.  Cliquez ensuite sur **Ajouter un filtre**.

4.  Créez un filtre pour lequel **Utilisateur Office Communications Server** a la valeur **True**.

5.  Cliquez sur **Rechercher** pour rechercher les utilisateurs hérités d’Office Communications Server 2007 R2.

6.  Sélectionnez deux utilisateurs que vous souhaitez déplacer vers le pool Lync Server 2013. Dans cet exemple, nous allons déplacer les utilisateurs Chen Yang et Claus Hansen.
    
    ![Liste des utilisateurs affichée à partir de la recherche d’utilisateurs OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Liste des utilisateurs affichée à partir de la recherche d’utilisateurs OCS")  

7.  Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.

8.  Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

9.  Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur OK.
    
    ![Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination")  

10. Vérifiez que la colonne pool de serveurs d' **inscriptions** des utilisateurs contient désormais le pool Lync Server 2013, ce qui indique que les utilisateurs ont été déplacés avec succès.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer plusieurs utilisateurs à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Sur la ligne de commande, tapez ce qui suit et remplacez **utilisateur1** et **utilisateur2** par des noms d’utilisateur spécifiques que vous souhaitez déplacer et remplacer le nom de **domaine complet du pool\_** par le nom du pool de destination. Dans cet exemple, nous allons déplacer les utilisateurs Hao Chen et Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Exemple de cmdlet pour déplacer un utilisateur hérité](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Exemple de cmdlet pour déplacer un utilisateur hérité")  

3.  Sur la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -Identity "User1"

4.  L’identité du pool de serveurs d' **inscriptions** doit désormais pointer vers le pool que vous avez spécifié comme **nom de domaine complet du pool\_** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès. Répétez cette étape pour vérifier que **User2** a été déplacé.
    
    ![Sortie de l’applet de commande PowerShell Get-UsUser-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Sortie de l’applet de commande PowerShell Get-UsUser-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Pour déplacer tous les utilisateurs en même temps à l’aide de Lync Server 2013 Management Shell

Dans cet exemple, tous les utilisateurs ont été renvoyés au pool Office Communications Server 2007 R2 (pool01.contoso.net). À l’aide de Lync Server 2013 Management Shell, nous allons déplacer tous les utilisateurs en même temps vers le pool Lync Server 2013 (pool02.contoso.net).

1.  Ouvrez **Lync Server 2013 Management Shell**.

2.  Dans la ligne de commande, tapez le code suivant :
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Exemple de cmdlet permettant de déplacer tous les utilisateurs hérités dans un pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Exemple de cmdlet permettant de déplacer tous les utilisateurs hérités dans un pool")  

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


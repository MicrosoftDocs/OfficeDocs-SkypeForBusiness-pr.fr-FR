---
title: 'Lync Server 2013 : déplacer des utilisateurs vers un autre pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1feda518b1a15ce5b4622659b9e5df45044bcefa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Déplacer des utilisateurs vers un autre pool dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2018-02-09_

Vous pouvez utiliser le panneau de configuration Lync Server pour affecter des utilisateurs à un serveur ou un pool spécifique.

<div>


> [!TIP]  
> Le fait de transférer tous les utilisateurs existants d’un pool source exécutant Lync Server 2010 ou une version antérieure vers un pool de destination Lync Server 2013 dans un environnement Active Directory complexe peut ralentir la réplication Active Directory. Pour éviter cela, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs à partir de pools qui exécutent Lync Server 2010 ou une version antérieure séparément, ou vous pouvez utiliser Lync Server Management Shell pour déplacer des utilisateurs avec cmdlets. En outre, la fonctionnalité de filtrage fonctionne avec les utilisateurs de Lync Server 2013.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Pour déplacer les utilisateurs sélectionnés vers un autre serveur ou pool

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.

5.  Dans le tableau, sélectionnez un ou plusieurs utilisateurs dans la liste.

6.  Dans le menu **Action**, cliquez sur **Déplacer les utilisateurs sélectionnés vers le pool**.

7.  Dans **Déplacer des utilisateurs**, sélectionnez dans le champ **Pool de serveurs d’inscriptions de destination** le pool vers lequel vous souhaitez déplacer les utilisateurs.

8.  (Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    <div>
    

    > [!Caution]  
    > Si vous sélectionnez <STRONG>forcer</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées à ces conférences et contacts planifiés ne sont pas déplacées.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Pour déplacer tous les utilisateurs d’un seul serveur ou pool vers un autre serveur ou pool

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.

5.  Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateurs que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.

6.  Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.

7.  (Optionnel) Si le serveur ou le pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    <div>
    

    > [!Caution]  
    > Si vous sélectionnez <STRONG>forcer</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées à ces conférences et contacts planifiés ne sont pas déplacées.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Pour déplacer des utilisateurs d’un pool vers un autre pool à l’aide d’un filtre

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans **recherche d’utilisateur**, cliquez sur **recherche**, puis sur **Ajouter un filtre**.

5.  Dans les critères de recherche, sélectionnez **Pool de serveurs d’inscriptions**, **Égal à**, **Nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.

6.  Dans le menu **Action**, cliquez sur **Déplacer tous les utilisateurs vers le pool**.
    
    <div>
    

    > [!NOTE]  
    > Lorsqu’un filtre est appliqué à un ensemble d’utilisateurs existant, l’option <STRONG>déplacer tous les utilisateurs vers le pool</STRONG> est dans le contexte du sous-ensemble filtré des utilisateurs, et non pas de <STRONG><EM>tous</EM></STRONG> les utilisateurs possibles.

    
    </div>

7.  Dans **Déplacer des utilisateurs**, sélectionnez le pool contenant les comptes d’utilisateur que vous souhaitez déplacer à l’aide de l’option **Pool de serveurs d’inscriptions source**.

8.  Dans **Pool de serveurs d’inscriptions de destination**, sélectionnez le pool vers lequel vous souhaitez déplacer les utilisateurs.

9.  (Optionnel) Si le serveur ou pool de destination n’est pas disponible, activez la case à cocher **Forcer**.
    
    <div>
    

    > [!Caution]  
    > Si vous sélectionnez <STRONG>forcer</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées à ces conférences et contacts planifiés ne sont pas déplacées.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Pour déplacer des utilisateurs d’un pool vers un autre à l’aide des applets de commande Windows PowerShell

1.  En fonction de la façon dont vous exécutez les commandes Windows PowerShell (localement ou à distance), vous devez vous connecter en tant que membre des rôles d’administrateur Lync Server 2013 appropriés comme suit :
    
    1.  Si vous exécutez les commandes sur l’ordinateur local (par exemple, vous vous connectez directement à un serveur frontal) : Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, vous ouvrez une session sur votre ordinateur et exécutez les commandes à distance sur un serveur frontal Standard Edition) : à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou à CsAdministrator , ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Pour déplacer des utilisateurs individuels, utilisez la cmdlet Move-CsUser comme suit :
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Où l’utilisateur à déplacer est Pilar Ackerman, lequel sera déplacé depuis le pool d’accueil qui lui est actuellement affecté vers le pool pool01.contoso.net

4.  Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec la cmdlet **Get-CsUser** et passez l’ensemble d’utilisateurs obtenu à **Move-CsUser** :
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Les commandes combinées des cmdlets **Get-CsUser** et **Move-CsUser** peuvent donner le résultat suivant :
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


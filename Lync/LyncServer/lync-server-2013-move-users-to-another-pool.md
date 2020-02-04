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
ms.openlocfilehash: 7dffa2e7651e056d9dc14b1e261134783d0fd193
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Déplacer des utilisateurs vers un autre pool dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2018-02-09_

Vous pouvez utiliser le panneau de configuration de Lync Server pour attribuer des utilisateurs à un serveur ou un pool spécifique.

<div>


> [!TIP]  
> Le déplacement de tous les utilisateurs existants à partir d’un pool de sources qui exécute Lync Server 2010 ou une version antérieure vers un pool de destination Lync Server 2013 dans un environnement Active Directory complexe peut ralentir la réplication Active Directory. Pour éviter ce problème, vous pouvez utiliser des filtres de recherche pour déplacer des utilisateurs de pools exécutant Lync Server 2010 ou une version antérieure séparément, ou vous pouvez utiliser Lync Server Management Shell pour déplacer des utilisateurs avec des cmdlets. Par ailleurs, la fonctionnalité filtre fonctionne avec les utilisateurs de Lync Server 2013.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Pour déplacer des utilisateurs sélectionnés vers un autre serveur ou pool

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la boîte de dialogue **Rechercher des utilisateurs** , entrez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité, adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.

5.  Dans le tableau, sélectionnez un utilisateur ou des utilisateurs spécifiques dans la liste.

6.  Dans le menu **action** , cliquez sur **déplacer les utilisateurs sélectionnés vers le pool**.

7.  Dans **déplacer les utilisateurs**, sélectionnez le groupe dans lequel vous souhaitez déplacer les utilisateurs dans le **pool d’inscriptions de destination**.

8.  Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    <div>
    

    > [!Caution]  
    > Si vous sélectionnez l’option <STRONG>force</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées, telles que les conférences et les contacts planifiés, ne sont pas déplacées.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Pour déplacer tous les utilisateurs d’un serveur ou d’un pool vers un autre serveur ou pool

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans le menu **action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.

5.  Dans **déplacer les utilisateurs**, sélectionnez le groupe qui contient les comptes d’utilisateurs que vous voulez déplacer dans le **pool d’inscriptions sources**.

6.  Dans la **liste de bureaux**d’enregistrement de destination, sélectionnez le groupe auquel vous voulez déplacer les utilisateurs.

7.  Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    <div>
    

    > [!Caution]  
    > Si vous sélectionnez l’option <STRONG>force</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées, telles que les conférences et les contacts planifiés, ne sont pas déplacées.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Pour déplacer des utilisateurs d’un groupe vers un autre à l’aide d’un filtre

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la **recherche d’utilisateur**, cliquez sur **Rechercher**, puis sur Ajouter un **filtre**.

5.  Dans les critères de recherche, sélectionnez **pool de bureaux**d’enregistrement, sélectionnez **égal à**, sélectionnez **nom de domaine complet du pool actuel**, puis cliquez sur **Rechercher**.

6.  Dans le menu **action** , cliquez sur **déplacer tous les utilisateurs vers le pool**.
    
    <div>
    

    > [!NOTE]  
    > Lorsque vous appliquez un filtre à un ensemble d’utilisateurs existant, l’option <STRONG>déplacer tous les utilisateurs vers le pool</STRONG> est dans le contexte du sous-ensemble filtré d’utilisateurs, et non de <STRONG><EM>tous</EM></STRONG> les utilisateurs possibles.

    
    </div>

7.  Dans **déplacer les utilisateurs**, sélectionnez le groupe qui contient les comptes d’utilisateurs que vous voulez déplacer dans le **pool d’inscriptions sources**.

8.  Dans la **liste de bureaux**d’enregistrement de destination, sélectionnez le pool dans lequel vous voulez déplacer les utilisateurs.

9.  Facultatif Si le serveur de destination ou le pool n’est pas disponible, activez la case à cocher **forcer** .
    
    <div>
    

    > [!Caution]  
    > Si vous sélectionnez l’option <STRONG>force</STRONG>, le compte d’utilisateur est déplacé, mais les données utilisateur associées, telles que les conférences et les contacts planifiés, ne sont pas déplacées.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Pour déplacer des utilisateurs d’un pool à un autre à l’aide des cmdlets Windows PowerShell

1.  En fonction de la manière dont vous exécutez les commandes Windows PowerShell (autrement dit, localement ou à distance), vous devez vous connecter en tant que membre des rôles d’administrateur de Lync Server 2013 appropriés comme suit :
    
    1.  Si vous exécutez les commandes sur l’ordinateur local (par exemple, si vous vous connectez directement à un serveur frontal) : Connectez-vous à l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires comme décrit dans la rubrique [autorisations de configuration de délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Si vous exécutez les commandes à distance sur un autre ordinateur (par exemple, si vous ouvrez une session sur votre ordinateur et exécutez les commandes à distance sur un serveur frontal Standard Edition) : à partir d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou à CsAdministrator pour vous connecter à n’importe quel ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour déplacer des utilisateurs uniques, utilisez l’applet de passe Move-CsUser en procédant comme suit :
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Lorsque l’utilisateur se déplace, c’est l’utilisateur Pilar Arès, et l’utilisateur est déplacé de sa liste de ressources personnelles actuellement affectées au pool pool01.contoso.net

4.  Pour déplacer un grand nombre d’utilisateurs, utilisez des filtres avec l’applet de passe **Get-Csuser** et transmettez le jeu d’utilisateurs obtenu à **Move-Csuser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Les commandes combinées de **Get-Csuser** et **Move-Csuser** peuvent être à l’origine :
    
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


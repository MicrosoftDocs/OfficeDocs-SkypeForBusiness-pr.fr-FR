---
title: 'Lync Server 2013 : Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 523907fbf4bc4cca93be8e529b6b607b43f0ea87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Si un utilisateur a été activé pour Lync Server, vous pouvez configurer une Fédération SIP, une Fédération d’utilisateurs distants et une connectivité de messagerie instantanée publique dans le panneau de configuration de Lync Server en appliquant les stratégies appropriées à des utilisateurs spécifiques. Par exemple, si vous avez créé une stratégie pour prendre en charge l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur pour que l’utilisateur puisse se connecter à Lync Server à partir d’un emplacement distant et collaborer avec des utilisateurs internes à partir de l’emplacement distant.

<div>


> [!NOTE]  
> Pour prendre en charge l’accès utilisateur externe, vous devez activer la prise en charge de chaque type d’accès des utilisateurs externes que vous voulez prendre en charge, et configurer les stratégies et autres options appropriées pour contrôler son utilisation. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configuring-support-for-external-user-access.md">configuration de la prise en charge de l’accès des utilisateurs externes dans Lync server 2013</A> dans la documentation de déploiement ou gestion de la <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Fédération et de l’accès externe à Lync Server 2013</A> dans la documentation sur les opérations.



</div>

Suivez la procédure décrite dans cette rubrique pour appliquer une stratégie d’accès aux utilisateurs externes précédemment créée à un ou plusieurs comptes d’utilisateurs.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur de Lync Server** sous **stratégie d’accès externe**, sélectionnez la stratégie d’utilisateur que vous voulez appliquer.
    
    <div>
    

    > [!NOTE]  
    > Les <STRONG> &lt;paramètres&gt; automatiques</STRONG> appliquent le serveur par défaut ou les paramètres de stratégie globale.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Attribution de stratégies d’accès externe par utilisateur à l’aide des applets de cmdlet Windows PowerShell

Les stratégies d’accès externe par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de l’applet de passe Grant-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Pour attribuer une stratégie d’accès externe par utilisateur à un utilisateur unique

  - Cette commande affecte le RedmondExternalAccessPolicy de stratégie d’accès externe par utilisateur à l’utilisateur Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Pour attribuer une stratégie d’accès externe par utilisateur à plusieurs utilisateurs

  - Cette commande affecte le USAExternalAccessPolicy de stratégie d’accès externe par utilisateur à tous les utilisateurs possédant des comptes dans l’unité d’organisation américaine d’Active Directory. Pour plus d’informations sur le paramètre de l’unité d’organisation utilisée dans cette commande, voir la documentation relative à l’applet de commande [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Pour annuler l’affectation d’une stratégie d’accès externe par utilisateur

  - Cette commande annule l’affectation d’une stratégie d’accès externe par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>


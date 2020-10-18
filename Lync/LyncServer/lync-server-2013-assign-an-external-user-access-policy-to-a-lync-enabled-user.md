---
title: 'Lync Server 2013 : attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync'
description: 'Lync Server 2013 : affectez une stratégie d’accès des utilisateurs externes à un utilisateur à extension Lync.'
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
ms.openlocfilehash: 2be3ea52e6e44400b3967d7c3346da2297220675
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573460"
---
# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Affectation d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Si un utilisateur a été activé pour Lync Server, vous pouvez configurer la Fédération SIP, la Fédération XMPP, l’accès des utilisateurs distants et la connectivité PIC (public Instant Messaging) dans le panneau de configuration Lync Server en appliquant les stratégies appropriées à des utilisateurs spécifiques. Par exemple, si vous avez créé une stratégie pour prendre en charge l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur avant de pouvoir se connecter à Lync Server à partir d’un emplacement distant et collaborer avec les utilisateurs internes à partir de l’emplacement distant.

<div>


> [!NOTE]  
> Pour prendre en charge l’accès des utilisateurs externes, vous devez activer la prise en charge pour chaque type d’accès d’utilisateur externe à prendre en charge, puis configurer les stratégies appropriées et d’autres options afin de contrôler son utilisation. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-configuring-support-for-external-user-access.md">configuration de la prise en charge de l’accès des utilisateurs externes dans Lync server 2013</A> dans la documentation de déploiement ou gestion de la <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Fédération et de l’accès externe à Lync Server 2013</A> dans la documentation des opérations.



</div>

La procédure de cette rubrique vous permet d’appliquer une stratégie d’accès des utilisateurs externes créée précédemment à un ou plusieurs comptes d’utilisateurs.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  Dans **Modifier l’utilisateur Lync Server** sous **Stratégie d’accès externe**, sélectionnez la stratégie d’utilisateur à appliquer.
    
    <div>
    

    > [!NOTE]  
    > Les paramètres <STRONG> &lt; automatiques &gt; </STRONG> appliquent les paramètres de stratégie globale ou de serveur par défaut.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Affectation de Per-User des stratégies d’accès externe à l’aide d’applets de commande Windows PowerShell

Les stratégies d’accès externe par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de l’applet de commande Grant-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Pour affecter une stratégie d’accès externe par utilisateur à un seul utilisateur

  - Cette commande permet d’affecter la stratégie d’accès externe par utilisateur RedmondExternalAccessPolicy à l’utilisateur Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Pour affecter une stratégie d’accès externe par utilisateur à plusieurs utilisateurs

  - Cette commande permet d’affecter la stratégie d’accès externe par utilisateur USAExternalAccessPolicy à tous les utilisateurs qui possèdent des comptes dans l’unité d’organisation (OU) UnitedStates dans Active Directory. Pour plus d’informations sur le paramètre OU utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Pour annuler l’affectation d’une stratégie d’accès externe par utilisateur

  - Cette commande annule l’affectation d’une stratégie d’accès externe par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>


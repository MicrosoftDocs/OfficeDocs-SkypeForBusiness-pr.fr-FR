---
title: 'Lync Server 2013 : Délégation du contrôle administratif de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2acecec7a4b6543bb5dd22720af7a3f9aab62137
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Délégation du contrôle administratif de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-22_

Dans Lync Server 2013, les tâches d’administration sont déléguées aux utilisateurs à l’aide de la nouvelle fonctionnalité de contrôle d’accès basée sur les rôles (RBAC). Lorsque vous installez Lync Server, un certain nombre de rôles RBAC sont créés pour vous. Ces rôles correspondent aux groupes de sécurité universelles dans les services de domaine Active Directory. Par exemple, le rôle RBAC CsHelpDesk correspond au groupe CsHelpDesk figurant dans le conteneur utilisateurs dans les services de domaine Active Directory (AD FS). Par ailleurs, chaque rôle RBAC est associé à un ensemble de cmdlets Windows PowerShell Lync Server. Ces applets de contrôle représentent les tâches qui peuvent être effectuées par les utilisateurs auxquels le rôle RBAC donné a été attribué. Par exemple, le rôle CsHelpDesk a été affecté aux cmdlets Lock-CsClientPin et UnlockCsClientPin. Cela signifie que les utilisateurs qui ont été attribués au rôle CsHelpDesk peuvent verrouiller ou déverrouiller des numéros de broche d’utilisateur. Toutefois, le rôle CsHelpDesk n’a pas été affecté à l’applet de nouvelle applet de nouveau CsVoicePolicy. Cela signifie que les utilisateurs qui ont été affectés au rôle CsHelpDesk ne peuvent pas créer de nouvelles stratégies vocales.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Affichage d’informations sur les rôles RBAC

Vous pouvez récupérer des informations de base sur vos rôles RBAC en exécutant la commande suivante à partir de Lync Server Management Shell:

    Get-CsAdminRole

Gardez à l’esprit que l’identité du rôle RBAC (par exemple, CsVoiceAdministrator) est associée à un groupe de sécurité figurant dans le conteneur utilisateurs dans les services de domaine Active Directory (AD DS).

Pour afficher une liste des applets de commande attribuées à un rôle, utilisez une commande semblable à celle-ci:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Attribution d’un rôle RBAC à un utilisateur

Pour attribuer un rôle RBAC à un utilisateur, vous devez l’ajouter au groupe de sécurité Active Directory approprié. Par exemple, pour affecter le rôle CsLocationAdministrator à un utilisateur, vous devez ajouter cet utilisateur au groupe CsLocationAdministrator. Pour cela, procédez comme suit:

**Pour affecter un utilisateur à un groupe de sécurité**

1.  À l’aide d’un compte qui dispose des autorisations nécessaires pour modifier l’appartenance à un groupe Active Directory, connectez-vous à un ordinateur sur lequel sont installés les utilisateurs et ordinateurs Active Directory.

2.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **utilisateurs et ordinateurs Active Directory**.

3.  Dans utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine, puis cliquez sur le conteneur **utilisateurs** .

4.  Cliquez avec le bouton droit sur le groupe de sécurité **CsLocationAdministrator**, puis cliquez sur **Propriétés**.

5.  Dans la boîte de dialogue **Propriétés** , sous l’onglet **membres** , cliquez sur **Ajouter**.

6.  Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes** , entrez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe (par exemple, **Ken Myer**) dans la zone **Entrez les noms des objets à sélectionner** , puis cliquez sur **OK**.

7.  Dans la boîte de dialogue **Propriétés** , cliquez sur **OK**.

Pour vérifier que le rôle RBAC a été affecté, utilisez l’applet de contrôle [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , en transmettant l’applet de contrôle sAMAccountName (nom de connexion Active Directory) de l’utilisateur. Par exemple, exécutez la commande suivante à partir de Lync Server Management Shell:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>


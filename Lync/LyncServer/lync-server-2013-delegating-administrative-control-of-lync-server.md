---
title: 'Lync Server 2013 : délégation du contrôle administratif de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93985818c62b195227323f4c0f6d5030db1f16f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Délégation du contrôle administratif de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Dans Lync Server 2013, les tâches d’administration sont déléguées aux utilisateurs à l’aide de la nouvelle fonctionnalité de contrôle d’accès basé sur un rôle (RBAC). Lorsque vous installez Lync Server, un certain nombre de rôles RBAC sont créés pour vous. Ces rôles correspondent à des groupes de sécurité universels dans les services de domaine Active Directory. Par exemple, le rôle RBAC CsHelpDesk correspond au groupe CsHelpDesk figurant dans le conteneur utilisateurs dans les services de domaine Active Directory. En outre, chaque rôle RBAC est associé à un ensemble d’applets de commande Lync Server Windows PowerShell. Ces applets de commande représentent les tâches qui peuvent être effectuées par les utilisateurs auxquels le rôle RBAC donné a été attribué. Par exemple, les applets de commande Lock-CsClientPin et UnlockCsClientPin ont été affectées au rôle CsHelpDesk. Cela signifie que les utilisateurs auxquels le rôle CsHelpDesk a été attribué peuvent verrouiller et déverrouiller les numéros de code confidentiel de l’utilisateur. Cependant, l’applet de commande New-CsVoicePolicy n’a pas été affectée au rôle CsHelpDesk. Par conséquent, les utilisateurs auxquels le rôle CsHelpDesk a été affecté ne peuvent pas créer de nouvelles stratégies de voix.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Affichage des informations sur les rôles RBAC

Vous pouvez récupérer des informations de base sur vos rôles RBAC en exécutant la commande suivante à partir de Lync Server Management Shell :

    Get-CsAdminRole

N’oubliez pas que l’identité du rôle RBAC (par exemple, CsVoiceAdministrator) a un mappage direct à un groupe de sécurité se trouvant dans le conteneur utilisateurs des services de domaine Active Directory.

Pour obtenir une liste des applets de commande qui sont affectées à un rôle, utilisez une commande similaire à celle-ci :

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Attribution d’un rôle RBAC à un utilisateur

Pour attribuer un rôle RBAC à un utilisateur, vous devez ajouter cet utilisateur au groupe de sécurité Active Directory approprié. Par exemple, pour affecter le rôle CsLocationAdministrator à un utilisateur, vous devez ajouter cet utilisateur au groupe CsLocationAdministrator. Pour cela, effectuez la procédure suivante :

**Pour affecter un utilisateur à un groupe de sécurité**

1.  En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.

2.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.

3.  Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur **Utilisateurs**.

4.  Cliquez avec le bouton droit sur le groupe de sécurité **CsLocationAdministrator**, puis cliquez sur **Propriétés**.

5.  Dans la boîte de dialogue **Propriétés**, sous l’onglet **Membres**, cliquez sur **Ajouter**.

6.  Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes**, tapez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe (par exemple, **Ken Myer**) dans la zone **Entrer les noms des objets à sélectionner**, puis cliquez sur **OK**.

7.  Dans la boîte de dialogue **Propriétés**, cliquez sur **OK**.

Pour vérifier que le rôle RBAC a été affecté, utilisez l’applet de commande [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment), en indiquant le nom SamAccountName (nom de connexion Active Directory) de l’utilisateur. Par exemple, exécutez la commande suivante à partir de Lync Server Management Shell :

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>


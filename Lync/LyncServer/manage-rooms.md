---
title: Gérer les salles
description: Gérer les salles.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be093e14a68639fdde73b58936e1b2f5cf4424cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544590"
---
# <a name="manage-rooms"></a>Gérer les salles

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Pour créer une salle de serveur de conversation permanente

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> -PersistentChatPoolFqdn n’est pas requis si l’un des éléments suivants est vrai : 
> <UL>
> <LI>
> <P>Il n’existe qu’un seul pool de serveurs de conversation permanente.</P>
> <LI>
> <P>Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.</P>
> <LI>
> <P>Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.</P></LI></UL>



</div>

Pour modifier une salle de serveur de conversation permanente

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell : les membres, les responsables et les présentateurs peuvent être définis simultanément. Ils doivent tous être le sous-ensemble de AllowedMembers moins DeniedMembers de la catégorie Hôte. Une chambre avec type=normal ne peut pas avoir de Présentateurs.

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a>Créer, atteindre, configurer, effacer ou supprimer une salle

Pour créer une nouvelle salle

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

Pour configurer une salle

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

Pour atteindre une salle

    Get-CsPersistentChatRoom -Identity <String>

ou

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

où –le filtre ne prend en charge que le nom et la description, et vous permet de rechercher des salles dont le nom/la description correspond à la chaîne de mot clé. PoolFqdn recherche dans un pool de serveurs de conversation permanente donné.

Pour effacer une salle et effacer les messages d’une salle

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

ou

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

Pour supprimer une salle

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

ou

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>


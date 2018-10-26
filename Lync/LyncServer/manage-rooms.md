---
title: Gestion des salles
TOCTitle: Gestion des salles
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205292(v=OCS.15)
ms:contentKeyID: 49298951
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des salles

 

_**Dernière rubrique modifiée :** 2013-02-21_

Pour créer une nouvelle salle de serveur de conversations permanentes

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

> [!IMPORTANT]  
> -PersistentChatPoolFqdn n’est pas requis si l’un des éléments suivants est vrai :<ul>
> <li><p>Il n’existe qu’un seul pool de serveurs de conversations permanentes.</p></li>
> <li><p>Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.</p></li>
> <li><p>Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.</p></li></ul>


Pour apporter des modifications à une salle de serveur de conversations permanentes existante

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell : les Membres, Responsables et Présentateurs peuvent être définis en même temps. Ils doivent tous être le sous-ensemble de AllowedMembers moins DeniedMembers de la catégorie Hôte. Une chambre avec type=normal ne peut pas avoir de Présentateurs.

## Créer, atteindre, configurer, effacer ou supprimer une salle

Pour créer une nouvelle salle

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

Pour configurer une salle

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

Pour atteindre une salle

    Get-CsPersistentChatRoom -Identity <String>

ou

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

où –le filtre ne prend en charge que le nom et la description, et vous permet de rechercher des salles dont le nom/la description correspond à la chaîne de mot clé. PoolFqdn recherche dans un pool de serveurs de conversations permanentes donné.

Pour effacer une salle et effacer les messages d’une salle

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

ou

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

Pour supprimer une salle

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

ou

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]


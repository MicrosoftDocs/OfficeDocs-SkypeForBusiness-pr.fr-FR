---
title: Gestion des catégories
TOCTitle: Gestion des catégories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204719(v=OCS.15)
ms:contentKeyID: 49296418
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des catégories

 

_**Dernière rubrique modifiée :** 2012-10-06_

Pour créer une catégorie serveur de conversations permanentes

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

> [!IMPORTANT]  
> PersistentChatPoolFqdn n’est nécessaire que si plusieurs pool de serveurs de conversations permanentes existent.

Pour modifier la catégorie serveur de conversations permanentes existante

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

Windows PowerShell : les membres autorisés, les membres non autorisés et les créateurs peuvent être définis simultanément. Les créateurs doivent constituer le sous-ensemble des membres autorisés moins les membres non autorisés. Vous pouvez également définir les propriétés d’une catégorie en même temps que les membres et les créateurs.

## Créer, obtenir, définir ou supprimer une catégorie

Pour créer une catégorie

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

Pour obtenir une catégorie

    Get-CsPersistentChatCategory -Identity <String>

ou

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

Pour définir une catégorie

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

ou

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

Pour supprimer une catégorie

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

ou

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]


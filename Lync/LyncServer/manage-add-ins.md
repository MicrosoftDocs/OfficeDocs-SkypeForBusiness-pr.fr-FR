---
title: Gestion des compléments
TOCTitle: Gestion des compléments
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205193(v=OCS.15)
ms:contentKeyID: 49298626
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des compléments

 

_**Dernière rubrique modifiée :** 2012-10-06_

Pour créer un nouveau complément de serveur de conversations permanentes

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

## Créer, obtenir, définir ou supprimer un complément

Pour créer un nouveau complément

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

> [!IMPORTANT]  
> PersistentChatPoolFqdn &lt;String&gt; est requis uniquement s’il y a plus d’un pool de serveurs de conversations permanentes.

Pour obtenir un complément

    Get-CsPersistentChatAddin -Identity <String>]

ou

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

Pour définir un complément

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

ou

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

Pour supprimer un complément

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

ou

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]


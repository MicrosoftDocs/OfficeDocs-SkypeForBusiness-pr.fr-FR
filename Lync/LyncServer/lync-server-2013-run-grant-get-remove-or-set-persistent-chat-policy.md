---
title: "LS 2013 : Exéc, octroi, obtention, suppr. ou déf. d’une strat. de conv. Perm."
TOCTitle: Exécution, octroi, obtention, suppression ou définition d’une stratégie de conversation permanente
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204810(v=OCS.15)
ms:contentKeyID: 49296924
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exécution, octroi, obtention, suppression ou définition d’une stratégie de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

Pour créer une stratégie de conversation permanente

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

Pour accorder une stratégie de conversation permanente

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Pour obtenir une stratégie de conversation permanente

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

Pour supprimer une stratégie de conversation permanente

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

Pour définir une stratégie de conversation permanente

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]


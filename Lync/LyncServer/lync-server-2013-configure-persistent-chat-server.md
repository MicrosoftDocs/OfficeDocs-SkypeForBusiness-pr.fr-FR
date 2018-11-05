---
title: 'Lync Server 2013 : Configuration du serveur de conversation permanente'
TOCTitle: Configuration du serveur de conversation permanente
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205054(v=OCS.15)
ms:contentKeyID: 49297953
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Pour créer une nouvelle configuration du conversation permanente

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Pour obtenir la configuration de conversation permanente

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

Pour supprimer la configuration de conversation permanente

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

Pour définir la configuration de conversation permanente

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Pour Lync Server 2013, tout le trafic de service web est pris en charge par les serveurs frontauxLync Server 2013. C’est pourquoi, l’adresse gcweb01 sur le serveur de conversations permanentes n’est pas nécessaire. Nous prenons toujours en charge l’accès au service web interne, car nous fournissons le service web de transfert/téléchargement de fichiers sur le site web *interne* uniquement (pas sur le site web *externe* pour les utilisateurs distants).


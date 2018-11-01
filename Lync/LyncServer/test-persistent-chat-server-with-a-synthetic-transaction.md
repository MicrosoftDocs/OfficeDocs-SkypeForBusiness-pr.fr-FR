---
title: "Test du chat du serv. de conv. Perm. avec une transaction synthétique"
TOCtitle: "Test du chat du serv. de conv. Perm. avec une transaction synthétique"
ms:assetid: 414e43f3-0074-4ecf-a232-398de972cb24
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204837(v=OCS.15)
ms:contentKeyID: 49297012
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test du chat du serveur de conversation permanente avec une transaction synthétique

 

_**Dernière rubrique modifiée :** 2012-09-21_

Pour tester le serveur de conversations permanentes dans le cadre de l’envoi et de la réception de messages dans une salle de conversation entre deux utilisateurs

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] -TargetFqdn <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] 
        [-OutVerboseVariable <String>] [<CommonParameters>]

ou

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> [-RegistrarPort 
        <Int32>] -SenderCredential <PSCredential> -SenderSipAddress <String> [-TargetFqdn <String>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [<CommonParameters>]

ou

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable 
        <String>] [<CommonParameters>]


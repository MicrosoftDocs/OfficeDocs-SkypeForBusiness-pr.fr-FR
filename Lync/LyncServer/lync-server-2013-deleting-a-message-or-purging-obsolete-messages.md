---
title: 'Lync Server 2013 : Suppression d’un message ou purge de messages obsolètes'
TOCTitle: Suppression d’un message ou purge de messages obsolètes
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215874(v=OCS.15)
ms:contentKeyID: 49296987
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’un message ou purge de messages obsolètes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-05_

Un administrateur de conversation permanente peut supprimer un message d’une salle de conversation permanente (et éventuellement le remplacer par un autre message). De même, les administrateurs peuvent vider les messages obsolètes dans le cadre de la maintenance régulière afin de limiter la croissance de la base de données. Par exemple, cette commande Windows PowerShell supprime de la salle de conversation ITChatRoom tous les messages postés par l’utilisateur kenmyer@litwareinc.com :

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

Et ce message remplace tous les messages supprimés par une note indiquant que le message n’est plus disponible :

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

Pour plus d’informations, reportez-vous à la rubrique d’aide sur l’applet de commande [Remove-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPersistentChatMessage).


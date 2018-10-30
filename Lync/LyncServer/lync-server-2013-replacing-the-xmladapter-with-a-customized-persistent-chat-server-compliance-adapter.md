---
title: "Rempl. XmlAdapter par ad. de conf. perso. du serv. de conv. perm. dans LS 2013"
TOCtitle: "Rempl. XmlAdapter par ad. de conf. perso. du serv. de conv. perm. dans LS 2013"
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49891284
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remplacement du XmlAdapter par un adaptateur de conformité personnalisé du serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Vous pouvez écrire un adaptateur personnalisé au lieu d’utiliser le XmlAdapter installé avec le serveur de conversations permanentes. Pour ce faire, vous devez fournir un assembly .NET Framework contenant une classe publique qui implémente l’interface **IComplianceAdapter**. Vous devez placer cet assembly dans le dossier d’installation du serveur de conversations permanentes pour chaque serveur de votre pool de serveurs de conversations permanentes. Chacun des serveurs de conformité peut fournir des données de conformité à votre adaptateur, mais ils ne délivrent aucun duplicata des données de conformité à plusieurs instances de votre adaptateur.

## Implémentation de l’interface IComplianceAdapter

L’interface est définie dans l’assembly Compliance.dll de l’espace de noms `Microsoft.Rtc.Internal.Chat.Server.Compliance`. Elle définit deux méthodes que votre adaptateur personnalisé doit implémenter.

    void SetConfig(AdapterConfig config)

Le serveur de conformité de conversation permanente appelle cette méthode lors du premier chargement de l’adaptateur. La méthode `AdapterConfig` contient la configuration de conformité de conversation permanente correspondant à l’adaptateur de conformité.

    void Translate(ConversationCollection conversations)

Le serveur de conformité de conversation permanente appelle cette méthode à intervalles réguliers tant qu’il existe de nouvelles données à traduire. Cet intervalle de temps équivaut à `RunInterval` comme définit dans la configuration de conformité de conversation permanente.

`ConversationCollection` contient les informations de conversation collectées lors du dernier appel de cette méthode.


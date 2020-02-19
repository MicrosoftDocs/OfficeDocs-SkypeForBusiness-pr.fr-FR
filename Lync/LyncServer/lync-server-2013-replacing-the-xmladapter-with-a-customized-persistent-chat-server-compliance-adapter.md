---
title: 'Lync Server 2013 : remplacement de XmlAdapter par une carte de conformité de serveur de conversation permanente personnalisée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0c1e001270e7a51e35d857625c77146f9a62e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Remplacement de XmlAdapter par une carte de conformité de serveur de conversation permanente personnalisée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Vous pouvez écrire un adaptateur personnalisé au lieu d’utiliser XmlAdapter qui est installé avec le serveur de conversation permanente. Pour ce faire, vous devez fournir un assembly .NET Framework contenant une classe publique qui implémente l’interface **IComplianceAdapter**. Vous devez placer cet assembly dans le dossier d’installation du serveur de conversation permanente de chaque serveur de votre pool de serveurs de conversation permanente. Chacun des serveurs de conformité peut fournir des données de conformité à votre adaptateur, mais ils ne délivrent aucun duplicata des données de conformité à plusieurs instances de votre adaptateur.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Implémentation de l’interface IComplianceAdapter

L’interface est définie dans l’assembly. dll de l’espace `Microsoft.Rtc.Internal.Chat.Server.Compliance`de noms. Elle définit deux méthodes que votre adaptateur personnalisé doit implémenter.

    void SetConfig(AdapterConfig config)

Le serveur de conformité de conversation permanente appellera cette méthode lors du premier chargement de la carte. Le `AdapterConfig` contient la configuration de la conformité de conversation permanente qui est pertinente pour la carte de conformité.

    void Translate(ConversationCollection conversations)

Le serveur de conformité de conversation permanente appelle cette méthode à intervalles réguliers tant qu’il y a de nouvelles données à traduire. Cet intervalle de temps est égal à `RunInterval` l’comme défini dans la configuration de la conformité de conversation permanente.

`ConversationCollection` Contient les informations de conversation collectées lors du dernier appel de cette méthode.

</div>

</div>

<span> </span>

</div>

</div>

</div>


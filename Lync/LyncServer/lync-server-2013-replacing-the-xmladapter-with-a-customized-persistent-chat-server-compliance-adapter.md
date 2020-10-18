---
title: 'Lync Server 2013 : remplacement de XmlAdapter par une carte de conformité de serveur de conversation permanente personnalisée'
description: 'Lync Server 2013 : remplacement de XmlAdapter par une carte de conformité de serveur de conversation permanente personnalisée.'
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
ms.openlocfilehash: 3a90b4df7df42ffdc6c55e9b551b0eb53d07ab1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576140"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="4cb81-103">Remplacement de XmlAdapter par une carte de conformité de serveur de conversation permanente personnalisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cb81-103">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cb81-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4cb81-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4cb81-105">Vous pouvez écrire un adaptateur personnalisé au lieu d’utiliser XmlAdapter qui est installé avec le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="4cb81-105">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="4cb81-106">Pour ce faire, vous devez fournir un assembly .NET Framework contenant une classe publique qui implémente l’interface **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="4cb81-106">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="4cb81-107">Vous devez placer cet assembly dans le dossier d’installation du serveur de conversation permanente de chaque serveur de votre pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="4cb81-107">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="4cb81-108">Chacun des serveurs de conformité peut fournir des données de conformité à votre adaptateur, mais ils ne délivrent aucun duplicata des données de conformité à plusieurs instances de votre adaptateur.</span><span class="sxs-lookup"><span data-stu-id="4cb81-108">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="4cb81-109">Implémentation de l’interface IComplianceAdapter</span><span class="sxs-lookup"><span data-stu-id="4cb81-109">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="4cb81-110">L’interface est définie dans l’assembly Compliance.dll dans l’espace de noms `Microsoft.Rtc.Internal.Chat.Server.Compliance` .</span><span class="sxs-lookup"><span data-stu-id="4cb81-110">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="4cb81-111">Elle définit deux méthodes que votre adaptateur personnalisé doit implémenter.</span><span class="sxs-lookup"><span data-stu-id="4cb81-111">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="4cb81-112">Le serveur de conformité de conversation permanente appellera cette méthode lors du premier chargement de la carte.</span><span class="sxs-lookup"><span data-stu-id="4cb81-112">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="4cb81-113">Le `AdapterConfig` contient la configuration de la conformité de conversation permanente qui est pertinente pour la carte de conformité.</span><span class="sxs-lookup"><span data-stu-id="4cb81-113">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="4cb81-114">Le serveur de conformité de conversation permanente appelle cette méthode à intervalles réguliers tant qu’il y a de nouvelles données à traduire.</span><span class="sxs-lookup"><span data-stu-id="4cb81-114">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="4cb81-115">Cet intervalle de temps est égal à l' `RunInterval` comme défini dans la configuration de la conformité de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="4cb81-115">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="4cb81-116">`ConversationCollection`Contient les informations de conversation collectées lors du dernier appel de cette méthode.</span><span class="sxs-lookup"><span data-stu-id="4cb81-116">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


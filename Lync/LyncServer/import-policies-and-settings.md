---
title: Importer des stratégies et des paramètres
description: Importer des stratégies et des paramètres.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569030"
---
# <a name="import-policies-and-settings"></a><span data-ttu-id="504a3-103">Importer des stratégies et des paramètres</span><span class="sxs-lookup"><span data-stu-id="504a3-103">Import policies and settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="504a3-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="504a3-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="504a3-105">Après avoir fusionné les informations de topologie Office Communications Server 2007 R2 avec votre pool pilote Lync Server 2013, vous devez exécuter une cmdlet Lync Server 2013 Management Shell pour migrer vos stratégies et paramètres de configuration Office Communications Server 2007 R2 vers votre pool de pilote Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="504a3-105">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="504a3-106">L’applet de commande **Import-applet cslegacyconfiguration** importe des stratégies, des itinéraires de communications vocales, des plans de numérotation, des URL d’Office Communicator Web Access et des numéros d’accès entrant vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="504a3-106">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="504a3-107">Pour migrer les stratégies et les paramètres</span><span class="sxs-lookup"><span data-stu-id="504a3-107">To migrate policies and settings</span></span>

1.  <span data-ttu-id="504a3-108">Sur le serveur frontal Lync Server 2013, démarrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="504a3-108">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="504a3-109">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="504a3-109">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="504a3-110">Une fois les stratégies importées, utilisez la procédure suivante pour afficher les stratégies importées dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="504a3-110">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="504a3-111">Pour afficher les stratégies importées</span><span class="sxs-lookup"><span data-stu-id="504a3-111">To view imported policies</span></span>

1.  <span data-ttu-id="504a3-112">Ouvrez le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="504a3-112">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="504a3-113">Cliquez sur **Routage des communications vocales** et affichez les stratégies importées.</span><span class="sxs-lookup"><span data-stu-id="504a3-113">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="504a3-114">Cliquez sur **Conférence** et affichez les stratégies importées.</span><span class="sxs-lookup"><span data-stu-id="504a3-114">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="504a3-115">Cliquez sur **Fédération et accès externe** et affichez les stratégies importées.</span><span class="sxs-lookup"><span data-stu-id="504a3-115">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="504a3-116">Cliquez sur **Surveillance et archivage** et affichez les stratégies importées.</span><span class="sxs-lookup"><span data-stu-id="504a3-116">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


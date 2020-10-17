---
title: 'Lync Server 2013 : publication de la base de données d’emplacements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 481a8406eeeec6fce25c19336519c4a9bf19da82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512371"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="ca19b-102">Publier la base de données d’emplacements à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca19b-102">Publish the location database from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca19b-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="ca19b-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="ca19b-104">Les nouveaux emplacements ajoutés à la base de données d’emplacements ne seront pas mis à la disposition du client tant qu’ils n’auront pas été publiés.</span><span class="sxs-lookup"><span data-stu-id="ca19b-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="ca19b-105">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ca19b-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="ca19b-106">**Publish-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="ca19b-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="ca19b-107">Si vous utilisez des passerelles ELIN (Emergency location Identification Number), vous devez également télécharger le numéros vers la base de données ALI (Automatic location identifier) de votre opérateur de téléphonie commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="ca19b-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="ca19b-108">Votre opérateur RTC peut exiger que vous utilisiez un format spécifique pour les enregistrements ELIN.</span><span class="sxs-lookup"><span data-stu-id="ca19b-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="ca19b-109">Pour plus d’informations, contactez votre opérateur RTC.</span><span class="sxs-lookup"><span data-stu-id="ca19b-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="ca19b-110">Vous pouvez exporter les enregistrements à partir de la base de données du service informations d’emplacement et les formater le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="ca19b-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="ca19b-111">Pour publier la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="ca19b-111">To publish the location database</span></span>

  - <span data-ttu-id="ca19b-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ca19b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="ca19b-113">Exécutez l’applet de commande suivante pour publier la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="ca19b-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>


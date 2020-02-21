---
title: 'Lync Server 2013 : configuration de la base de données d’emplacements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ff565c1d884fe2af9a49da6798e8c3e52cb38da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="54305-102">Configuration de la base de données d’emplacements dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54305-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54305-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="54305-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="54305-p101">Pour permettre aux clients de détecter automatiquement leur emplacement au sein d’un réseau, vous devez d’abord configurer la base de données d’emplacements. Si vous ne configurez pas de base de données d’emplacements et que l’option **Emplacement obligatoire** est définie sur **Oui** ou **Clause d’exclusion de responsabilité** dans la stratégie d’emplacement, l’utilisateur sera invité à entrer manuellement un emplacement.</span><span class="sxs-lookup"><span data-stu-id="54305-p101">To enable clients to automatically detect their location within a network, you first need to configure the location database. If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="54305-106">Pour configurer la base de données d’emplacements, vous devrez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="54305-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="54305-107">Remplir la base de données avec une correspondance des éléments réseau avec les emplacements.</span><span class="sxs-lookup"><span data-stu-id="54305-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="54305-108">Si vous utilisez une passerelle ELIN (Emergency location Identification Number), vous devez inclure le ELIN dans le \<champ\> CompanyName.</span><span class="sxs-lookup"><span data-stu-id="54305-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="54305-109">Valider les adresses par rapport à la base de données MSAG gérée par le fournisseur de service E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="54305-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="54305-110">Publier la base de données mise à jour.</span><span class="sxs-lookup"><span data-stu-id="54305-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54305-111">Vous pouvez également définir une base de données d’emplacements source secondaire pouvant être utilisée à la place de la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="54305-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="54305-112">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configure-a-secondary-location-information-service.md">la rubrique Configure a Secondary location information service in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="54305-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="54305-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="54305-113">In This Section</span></span>

  - [<span data-ttu-id="54305-114">Remplir la base de données d’emplacements dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54305-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="54305-115">Valider des adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54305-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="54305-116">Publier la base de données d’emplacements à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54305-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


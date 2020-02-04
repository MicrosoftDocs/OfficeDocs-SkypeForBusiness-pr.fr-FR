---
title: 'Lync Server 2013 : configurer la base de données de localisation'
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
ms.openlocfilehash: b2b15f0c679e9380a1f1a624f00f6c19384878fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="343eb-102">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="343eb-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="343eb-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="343eb-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="343eb-104">Pour permettre aux clients de détecter automatiquement leur emplacement au sein d’un réseau, vous devez d’abord configurer la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="343eb-104">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> <span data-ttu-id="343eb-105">Si vous ne configurez pas de base de données de géolocalisation **et que** la stratégie d’emplacement est définie sur **Oui** ou **exclusion de responsabilité**, l’utilisateur est invité à entrer manuellement un emplacement.</span><span class="sxs-lookup"><span data-stu-id="343eb-105">If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="343eb-106">Pour configurer la base de données de localisation, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="343eb-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="343eb-107">Remplissez la base de données avec une correspondance des éléments réseau avec les emplacements.</span><span class="sxs-lookup"><span data-stu-id="343eb-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="343eb-108">Si vous utilisez une passerelle ELIN, vous devez inclure la ELIN dans le \<champ CompanyName\> (région d’urgence).</span><span class="sxs-lookup"><span data-stu-id="343eb-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="343eb-109">Validez les adresses par rapport à la base de données MSAG gérée par le fournisseur de service E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="343eb-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="343eb-110">Publiez la base de données mise à jour.</span><span class="sxs-lookup"><span data-stu-id="343eb-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="343eb-111">Vous pouvez également définir une base de données source de emplacement secondaire qui peut être utilisée dans l’emplacement de la base de données de localisation.</span><span class="sxs-lookup"><span data-stu-id="343eb-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="343eb-112">Pour plus d’informations, voir <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurer un service d’information d’emplacement secondaire dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="343eb-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="343eb-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="343eb-113">In This Section</span></span>

  - [<span data-ttu-id="343eb-114">Peupler la base de données de localisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="343eb-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="343eb-115">Valider des adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="343eb-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="343eb-116">Publier la base de données de localisation à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="343eb-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


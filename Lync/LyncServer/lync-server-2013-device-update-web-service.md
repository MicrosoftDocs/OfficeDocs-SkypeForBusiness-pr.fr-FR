---
title: 'Lync Server 2013 : service web de mise à jour des dispositifs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9f7068943deabb90e5a87d95f35fecfbc30c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="5d8da-102">Service web de mise à jour des dispositifs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d8da-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d8da-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="5d8da-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="5d8da-104">Lync Server inclut le service Web de mise à jour d’appareils, qui est automatiquement installé dans le cadre du rôle Services Web.</span><span class="sxs-lookup"><span data-stu-id="5d8da-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="5d8da-105">Ce service vous permet de télécharger les mises à jour de Microsoft, de les tester, puis de déployer les mises à jour apportées vers des téléphones IP au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5d8da-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="5d8da-106">Vous pouvez également utiliser le service Web de mise à jour de l’appareil pour restaurer les appareils dans les versions antérieures de logiciels.</span><span class="sxs-lookup"><span data-stu-id="5d8da-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="5d8da-107">Cette section fournit des détails sur la façon de gérer le service Web de mise à jour de l’appareil et les mises à jour déployées à l’aide de journaux de mise à jour de l’appareil, de règles (Lync Phone Edition utilise des *règles* pour associer les mises à jour de version du microprogramme avec des périphériques matériels) et des paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="5d8da-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="5d8da-108">Pour plus d’informations sur le processus et les fonctionnalités de service Web de mise à jour d’appareils, voir [mise à jour d’appareils](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) dans la bibliothèque TechNet de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5d8da-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="5d8da-109">(Notez que le service Web de mise à jour de l’appareil, tel que tous les composants de Lync Phone Edition, fonctionne de la même façon que Lync Server 2013 comme pour Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="5d8da-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5d8da-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5d8da-110">In This Section</span></span>

  - [<span data-ttu-id="5d8da-111">Fichiers et journaux de mise à jour des appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d8da-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="5d8da-112">Règles de mise à jour des appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d8da-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="5d8da-113">Paramètres de configuration de la mise à jour des appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d8da-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="5d8da-114">Afficher les mises à jour logicielles des appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d8da-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d8da-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d8da-115">See Also</span></span>


<span data-ttu-id="5d8da-116">[Outils et services pour la gestion et la résolution des problèmes de périphériques](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5d8da-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


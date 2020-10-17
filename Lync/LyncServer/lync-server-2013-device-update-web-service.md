---
title: 'Lync Server 2013 : service Web de mise à jour des périphériques'
description: 'Lync Server 2013 : service Web de mise à jour des périphériques.'
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
ms.openlocfilehash: 45511d34ab99f295481472f2a3c14bf21da32ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565950"
---
# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="7c9dc-103">Service Web de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c9dc-103">Device Update Web service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c9dc-104">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7c9dc-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7c9dc-105">Lync Server inclut le service Web de mise à jour des périphériques, qui est automatiquement installé dans le cadre du rôle Services Web.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-105">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="7c9dc-106">Ce service vous permet de télécharger des mises à jour à partir de Microsoft, de les tester, puis de déployer les mises à jour sur les téléphones IP de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-106">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="7c9dc-107">Vous pouvez également faire appel au service web de mise à jour des périphériques pour restaurer les périphériques en rétablissant les versions logicielles précédentes.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-107">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="7c9dc-108">Cette section fournit des détails sur la façon de gérer le service Web de mise à jour des périphériques et des mises à jour déployées à l’aide des journaux de mise à jour des appareils, des règles (Lync Phone Edition utilise des *règles* pour associer les mises à jour de version de microprogramme aux périphériques matériels) et des paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-108">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="7c9dc-109">Pour plus d’informations sur le processus et les fonctionnalités du service Web de mise à jour des périphériques, voir [mise à jour des périphériques](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) dans la bibliothèque TechNet Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7c9dc-109">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="7c9dc-110">(Notez que le service Web de mise à jour des périphériques, comme tous les composants de Lync Phone Edition, fonctionne de la même manière avec Lync Server 2013 que avec Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="7c9dc-110">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7c9dc-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7c9dc-111">In This Section</span></span>

  - [<span data-ttu-id="7c9dc-112">Fichiers et journaux de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c9dc-112">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="7c9dc-113">Règles de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c9dc-113">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="7c9dc-114">Paramètres de configuration de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c9dc-114">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="7c9dc-115">Affichage des mises à jour logicielles pour les périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c9dc-115">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c9dc-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c9dc-116">See Also</span></span>


<span data-ttu-id="7c9dc-117">[Outils et services de gestion et de dépannage des appareils](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7c9dc-117">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


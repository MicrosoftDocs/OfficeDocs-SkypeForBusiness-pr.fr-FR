---
title: Gestion des paramètres de configuration du service de journalisation centralisé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb3b16210b3fac64c0c5bd7886849da7dd0d065
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="83fab-102">Gestion des paramètres de configuration du service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fab-102">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83fab-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="83fab-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="83fab-104">Le service de journalisation centralisé est contrôlé et configuré à l’aide de paramètres et de paramètres créés et utilisés par le contrôleur de service de journalisation centralisé (CLSController) pour envoyer des commandes à l’agent de service de journalisation centralisé de l’ordinateur ( CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="83fab-104">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="83fab-105">L’agent traite les commandes qui lui sont envoyées et (dans le cas d’une commande de démarrage) utilise la configuration des scénarios, fournisseurs, taille du journal, durée du suivi et indicateurs pour commencer à collecter des journaux de suivi conformément aux informations de configuration fournies.</span><span class="sxs-lookup"><span data-stu-id="83fab-105">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="83fab-106">Les applets de connexion Windows PowerShell n’ayant pas été répertoriées pour le service de journalisation centralisée sont conçues pour une utilisation avec des déploiements sur site de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83fab-106">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="83fab-107">Même si cela semble fonctionner, les cmdlets suivantes ne sont pas conçues pour fonctionner avec les déploiements locaux de Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="83fab-107">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="83fab-108"><STRONG>Cmdlets CsClsRegion :</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>et <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span><span class="sxs-lookup"><span data-stu-id="83fab-108"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="83fab-109"><STRONG>Cmdlets CsClsSearchTerm :</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> et <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span><span class="sxs-lookup"><span data-stu-id="83fab-109"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="83fab-110"><STRONG>Cmdlets CsClsSecurityGroup :</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>et <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span><span class="sxs-lookup"><span data-stu-id="83fab-110"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="83fab-111">Les paramètres définis dans ces cmdlets n’entravent pas ou risquent de provoquer un comportement indésirable, mais ils sont conçus pour une utilisation avec Microsoft Office 365 et ne produiront pas les résultats attendus dans les déploiements sur site.</span><span class="sxs-lookup"><span data-stu-id="83fab-111">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="83fab-112">Ce n’est pas qu’il n’y a aucune utilisation pour ces applets de configuration dans les déploiements sur site, mais leur utilisation est un sujet plus avancé qui n’est pas abordé dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="83fab-112">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="83fab-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="83fab-113">In This Section</span></span>

<span data-ttu-id="83fab-114">Les rubriques de cette section définissent les options de configuration, les paramètres et les paramètres du service de journalisation centralisé.</span><span class="sxs-lookup"><span data-stu-id="83fab-114">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="83fab-115">Pour plus d’informations sur la configuration du service de journalisation centralisé, la façon de récupérer les paramètres de configuration, la création de scénarios, la gestion des groupes de sécurité pour le service de journalisation centralisé, la recherche, etc., est contenue dans les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="83fab-115">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="83fab-116">Gestion de l’ordinateur, du site et de la configuration du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fab-116">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="83fab-117">Configuration de fournisseurs pour le service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fab-117">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="83fab-118">Configuration de scénarios pour le service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fab-118">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83fab-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83fab-119">See Also</span></span>


[<span data-ttu-id="83fab-120">Présentation du service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fab-120">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="83fab-121">Cmdlets d’enregistrement centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fab-121">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

